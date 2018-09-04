# cocos2d-x-bugfixes-list

***

## Android Bug-Fix: Game stops music at opening
- https://github.com/cocos2d/cocos2d-x/issues/18465

***

## iOS Bug-Fix: App Crash / Audio Interruption
In file `cocos2d_lib/audio/iso/CDAudioManager.m` replace
```
	NSSelectorFromString(@"handleInterruption")
```
to
```
	@selector(handleInterruption:)
```

***

## Cocos2d-x 3.16: Rollback support win10
- http://discuss.cocos2d-x.org/t/windows10-and-cocos2dx-3-16/39396
- https://github.com/cocos2d/cocos2d-x/pull/18394/commits/c3e53da6a7768e0474ba3c365c4cb9aecba63be0

***

## Cocos2d-x 3.16: Fix build problem with Android Studio 3
- https://github.com/cocos2d/cocos2d-x/issues/18506

***

## Cocos2d-x 3.X: Fix problem with landscape content draw on user back to app

- https://discuss.cocos2d-x.org/t/incorrect-content-drawing-on-android-for-landscape-mode/42434
- https://discuss.cocos2d-x.org/t/resolution-problem-while-launching-game-through-push-notification-from-lock-screen/22254/3

Modify onSizeChanged method in Cocos2dxGLSurfaceView.java as below
```
    @Override
    protected void onSizeChanged(final int pNewSurfaceWidth, final int pNewSurfaceHeight, final int pOldSurfaceWidth, final int pOldSurfaceHeight) {
        if(!this.isInEditMode()) {
               if(pNewSurfaceWidth < pNewSurfaceHeight)
                       this.mCocos2dxRenderer.setScreenWidthAndHeight(pNewSurfaceHeight, pNewSurfaceWidth); 
               else
            	this.mCocos2dxRenderer.setScreenWidthAndHeight(pNewSurfaceWidth, pNewSurfaceHeight);
        }
    }
```
*Note: Do this if your game is in landscape mode*

***

## iOS: Add iPhone-X support
Check files in folder

***
