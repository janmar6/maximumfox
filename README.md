# MaximumFox


### UserChrome.css
1. In `about:config` set `toolkit.legacyUserProfileCustomizations.stylesheets` to "True" for your custom themes to work.
2. In `about:support` in the big box you will find a `profile directory` with a `Open Directory` button.
3. Inside of that create a `chrome` folder, if it is not already there.
4. Put `userChrome.css` inside of `chrome`.


### Extensions which you have to install:
- [Tree Style Tabs](https://addons.mozilla.org/en-US/firefox/addon/tree-style-tab/)
- [Adaptive Tab Bar Color](https://addons.mozilla.org/en-US/firefox/addon/adaptive-tab-bar-colour/)


### TreeStyleTabs
1. Go to `about:addons`.
2. Click on `Tree Style Tab` -> `Preferences` -> `Open this options page in more wide space`(blue link at top right) -> `Advanced`.
3. Inside of the text box delete everything and copy-paste the contents of the `TreeStyleTabs.css`(Saved automatically).


### Adaptive Tab Bar Color
1. Go to `about:addons`.
2. Click on `Adaptive Tab Bar Color` -> `Preferences`.
3. Tick the box which says `Allow dark tab bar`.


### Restart FireFox
once you restart firefox everything should look good.

### Useful shortcuts
- To toggle Tree Style Tab, you can press `F1`.
- To focus on the nav bar, you can press `F6`.

}

/* Push tab labels slightly to the right so they're completely hidden in collapsed state, but still look fine while expanded. */
.tab .label {
  margin-left: 1em;
}

/* fix closebox */
.tab .closebox {
  margin-left:  0;
}

.tab .counter {
  margin-left:  auto;
  display: inline-block !important;
}

/* Hide .twisty and adjust margins so favicons have 7px on left. */
#tabbar:not(:hover) .tab .twisty {
  visibility: hidden;
  margin-left: -12px;
  transition-delay: var(--tst-sidepanel-hide-delay);
}


/* hide closebox unless needed */
.tab:not(:hover) .closebox {
  visibility: hidden;
}

/* Hide sound playing/muted button. */
.sound-button {
  margin-left: 0;
  display: inline-block;
  visibility: collapse;
}

.tab.audible .sound-button {
  visibility: visible;
  margin-left: 0.25em;
}

.tab:not([data-child-ids]) .counter {
  /* visibility: hidden; */
}

tab-item:not(.subtree-collapsed) .counter {
  visibility: hidden;
} 

/* Hide 'new tab' button. */
.newtab-button {
  display: none;
}

/* active tab */
.tab.active {
  background-color: rgba(255, 255, 255, 0.05) !important;
}

tab-item.active .highlighter::before {
  background-color: #fffd !important;
}

.tab:hover,
.tab.active:hover {
  background-color: inherit;
}
.tab.active .label {
  font-weight: bold;
  color: #f4f4f4 !important;
}
.tab .label,
.tab.active .label {
  border-bottom:  1px solid transparent;
}
.tab:hover .label,
.tab.active:hover .label {
  border-bottom:  1px dotted;
  min-width:  0 !important;
  flex-shrink:  1 !important;
  flex-grow:  unset !important;
}

/* pending / unloaded tabs */
.tab.discarded {
  background-color: #1d1d1d;
}
.tab.discarded .label {
  color: #efefefCC !important;
}
.tab.discarded:hover .label {
  color: #efefef !important;
}

/* Adjust style for tab that has sound playing. */
.tab.sound-playing .favicon::after,
.tab.muted .favicon::after {
  content: '🔊';
  z-index: var(--favicon-base-z-index);
  position: absolute;
  font-size: 0.5em;
  bottom: -0.35em;
  right: -0.7em;
}

/* Adjust style for tab that is muted. */
.tab.muted .favicon::after {
  content: '🔇';
}

/* Pinned tabs: */
/* Hide all non-active pinned tabs (these are included in top-bar instead) */
.tab.pinned {
  position: relative;
  max-width: none;
  width: auto;
  top: 0 !important;
  left: 0 !important;
}
.tab.pinned:not(.active) {
  display: none;
}
.tab.pinned .label,
.tab.pinned .label-content {
  opacity: 1;
  position: unset;
  padding-bottom: 0;
}
.tab.pinned .sound-button {
  position: relative;
  transform: none;
}
.tab.pinned .twisty {
  display: block;
  min-width: none;
  width: auto;
}
