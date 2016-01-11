#  Deserted
this repository is deserted,it is changed to <https://github.com/GreedBell/UICollectionView-ARDynamicHeightLayoutCell>

# Fork
fork from [UICollectionView-ARDynamicHeightLayoutCell](https://github.com/AugustRush/UICollectionView-ARDynamicHeightLayoutCell) of version v1.0

# UICollectionView+ARDynamicHeightLayoutCell

* An simple category for caculating autolayout UICollectionViewCell size. Automatic manage cell's size cache, automatic invalidate, most improve efficiency.

## Demo gif 

<img src="https://github.com/AugustRush/UICollectionView-ARDynamicHeightLayoutCell/blob/master/gif1.gif" width="320">
<img src="https://github.com/AugustRush/UICollectionView-ARDynamicHeightLayoutCell/blob/master/gif2.gif" width="320">

## Support

* A prototype cell in storyboard

* -registerNib:forCellReuseIdentifier:

* -registerClass:forCellReuseIdentifier:

## Usage

if your cell use autolayout , all you need just to do like this:

#### Fixed width

```
#import "UICollectionView+ARDynamicHeightLayoutCell.h"

-(CGSize)collectionView:(UICollectionView *)collectionView layout:(UICollectionViewLayout *)collectionViewLayout sizeForItemAtIndexPath:(NSIndexPath *)indexPath
{
    return [collectionView ar_sizeForCellWithIdentifier:@"DynamicHeightCell" fixedWidth:300 configuration:^(id cell) {

       //configuration your cell
        FeedModel *feed = self.feeds[indexPath.row];
        [cell filleCellWithFeed:feed];

    }];
}
```
#### Fixed height

```
#import "UICollectionView+ARDynamicHeightLayoutCell.h"

-(CGSize)collectionView:(UICollectionView *)collectionView layout:(UICollectionViewLayout *)collectionViewLayout sizeForItemAtIndexPath:(NSIndexPath *)indexPath
{
    return [collectionView ar_sizeForCellWithIdentifier:@"DynamicHeightCell" fixedHeight:400 configuration:^(id cell) {
    	//configuration your cell
           FeedModel *feed = self.feeds[indexPath.row];
           [cell filleCellWithFeed:feed];
	}
}
```

#### Dynamic size

```
#import "UICollectionView+ARDynamicHeightLayoutCell.h"

-(CGSize)collectionView:(UICollectionView *)collectionView layout:(UICollectionViewLayout *)collectionViewLayout sizeForItemAtIndexPath:(NSIndexPath *)indexPath
{
    return [collectionView ar_sizeForCellWithIdentifier:@"DynamicHeightCell" configuration:^(id cell) {
    	//configuration your cell
           FeedModel *feed = self.feeds[indexPath.row];
           [cell filleCellWithFeed:feed];
	}
}
```

## Install

pod 'UICollectionView-ARDynamicHeightLayoutCell_Bell'

## Release Versions

* v1.0.3

  fix the bug of crushing when device orientation changed

* v1.0.2
  
  fix the bug of cursh when using UIAlertView

* v1.0.1
  
  fix the bug crushing when more than one sections

* v1.0

   add cache for cell size height, improve efficiency（automatic invalidate）

* v0.7 

    add Support for StoryBoard prototype cell

* v0.6 

   fixed Height caculated bug and support Dynamic size cell

* v0.5 

    support to caculate size for UICollectionView Cell

## ToDo

* pre caculate cache

