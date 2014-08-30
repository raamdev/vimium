## My Vimium key bindings (Emacs-style).
This is a **full** set of key bindings (as of [Vimium](http://vimium.github.io/) v1.45); covering all Vimium functionality. I have tried to map all Vimium functionality to comparable Emacs functionality (whenever possible). In cases where there is no equivalent, those commands are prefixed by `<c-g>` (indicating (G)oogle Chrome; and because `<c-g>` does not conflict with other Emacs shortcuts at all).

_**Commented Shortcuts:** There are a few Emacs-style shortcuts that are simply not possible in Vimium. All of my shortcuts (including those which were not possible; i.e. where I used a decent alternative) have been commented below. This should help to clarify my rationale._

_**Compatibility:** All of these shortcuts were tested on Mac OS X (Mavericks). Please note that all of my shortcuts operate under the assumption that your Emacs Meta key is the `⌥` Alt/Option key. This really was my only choice, because the `⌘` key is already used in Chrome for shortcuts that come built into Chrome itself. Therefore, if you intend to use these shortcuts, I'd highly recommend that you use the `⌥` Alt/Option key as your Emacs Meta key; helps with consistency._


```bash
#########################################

unmapAll # Use Emacs-style bindings only.

#########################################

# Modifier Keys w/ Emacs Terminology:

# `<c-*>` = ⌃ Control Key; i.e. `C-*`.
# `<a-*>` = ⌥ Meta Key (Alt/Option); i.e. `M-*`.
# To clarify, `<a-*>` is `M-*` in the world of Emacs.

# `<m-*>` = ⌘ Command Key (Prone to Conflicts).
#   Avoid ⌘ key conflicts in Google Chrome.
#   It's good to avoid the ⌘ key altogether.
#   ~ See: http://bit.ly/VUvR7i

# The ⇧ Shift key is not used explicitly. However,
# all of these keyboard shortcuts are caSe-sensitive.
# Therefore, `<c-b>` is NOT the same as `<c-B>`.
# Meaning, the ⇧ Shift key **is** necessary in some cases.

#########################################

# Similar to Emacs `(next|previous)-line`.
map <c-n> scrollDown
map <c-p> scrollUp

# Similar to Emacs `(backward|forward)-char`.
map <c-b> scrollLeft
map <c-f> scrollRight

# Similar to Emacs `(beginning|end)-of-buffer`.
map <a-<> scrollToTop
map <a->> scrollToBottom

# Identical to Emacs `scroll-(left|right)`.
map <c-x>< scrollToLeft
map <c-x>> scrollToRight

# Identical to `scroll-(down|up)-command`.
map <a-v> scrollFullPageUp
map <c-v> scrollFullPageDown

# Identical to Emacs `scroll-(up|down)-line`
# No KBD shortcut in Emacs by default.
map <a-]> scrollPageDown
map <a-[> scrollPageUp

# Identical to Emacs `find-alternate-file`.
map <c-x><c-v> reload

# Not implemented in Emacs.
map <a-s> toggleViewSource

# Identical to Emacs `delete-window`.
map <c-x>0 removeTab

# Not implemented in Emacs.
map <c-g><c-u> copyCurrentUrl
map <c-g><c-l> LinkHints.activateModeToCopyLinkUrl

# Not implemented in Emacs.
map <c-g><c-o> openCopiedUrlInCurrentTab
map <c-g><c-O> openCopiedUrlInNewTab

# Not implemented in Emacs.
map <c-g>< goUp
map <c-g>/ goToRoot

# Not implemented in Emacs.
map <c-g><c-i> enterInsertMode

# Not implemented in Emacs.
map <c-g><c-f> focusInput

# Similar to Emacs `find-file`.
map <c-x><c-f> LinkHints.activateMode
map <c-x><c-F> LinkHints.activateModeToOpenInNewForegroundTab
map <c-x><a-f> LinkHints.activateModeWithQueue
map <c-x><a-F> LinkHints.activateModeToOpenInNewTab

# Similar to Emacs `list-directory`.
map <c-x><c-d> Vomnibar.activate
map <c-x><c-D> Vomnibar.activateInNewTab

# Similar to Emacs `switch-to-buffer`.
map <c-x>b Vomnibar.activateTabSelection

# Similar to Emacs `list-buffers`.
map <c-x><c-b> Vomnibar.activateBookmarks
map <c-x><c-B> Vomnibar.activateBookmarksInNewTab

# Not implemented in Emacs.
# Similar to Emacs `(previous|next)-buffer`.
# However, this uses `<c-g>` instead of `<c-x>`.
map <c-g><left> goPrevious
map <c-g><right> goNext

# Similar to Emacs `other-frame`.
# Also similar to Emacs `other-window`.
# The correct mapping is `<c-x>5o`, but not possible.
# Vimium doesn't support the `o` argument.
# Instead using `<c-x>o` here.
map <c-x>o nextFrame

# Similar to Emacs `set-mark-command`.
# Similar to Emacs `pop-global-mark`.
# Can't use `<c-<space>>` it conflicts w/ Chrome.
# In Chrome, `<space>` scrolls the current document.
map <c-@> Marks.activateCreateMode
map <c-x><c-@> Marks.activateGotoMode

# Similar to Emacs `isearch-forward`.
# Similar to Emacs `isearch-repeat-(forward|backward)`.
#------------------------------------------------------------------
# NOTE: Vimium doesn't support repeated `<c-s>`.
# Instead, use `<c-S>` to move to next result.
#------------------------------------------------------------------
# NOTE: `<c-S>` may conflict w/ SnagIt™. If you run this app,
# please remap SnagIt™ to resolve this potential conflict.
#------------------------------------------------------------------
# NOTE: Vimium requires that you press the `<enter>` key
# before shortcuts `<c-S>` and `<c-R>` will actually work.
#------------------------------------------------------------------
map <c-s> enterFindMode
map <c-S> performFind
map <c-r> performBackwardsFind
map <c-R> performBackwardsFind

# Not implemented in Emacs.
# Similar to Emacs `(backward|forward)-char`.
# However, this uses capitals w/ the shift key.
map <c-B> goBack
map <c-F> goForward

# Not implemented in Emacs.
# Similar to Emacs `(previous|next)-buffer`.
map <c-x><left> previousTab
map <c-x><right> nextTab

# Not implemented in Emacs.
# Similar to Emacs `(previous|next)-buffer`.
map <c-x><up> firstTab
map <c-x><down> lastTab

# Similar to Emacs `generate-new-buffer`.
# No KBD shortcut in Emacs by default.
map <c-g><c-t> createTab

# Similar to `clone-indirect-buffer-other-window`.
# The correct mapping is `<c-x>4c`, but not possible.
# Vimium doesn't support the `c` argument.
map <c-x>4 duplicateTab
# Should be <c-x>4c

# Not implemented in Emacs.
# Similar to Emacs `recover-file`.
# No KBD shortcut in Emacs by default.
map <c-g><c-r> restoreTab

# Similar to `make-frame-command`.
# The correct mapping is `<c-x>52`, but not possible.
# Vimium doesn't support the `2` argument.
map <c-x>5 moveTabToNewWindow
# Should be <c-x>52

# Not implemented in Emacs.
# Similar to `set-window-dedicated-p`.
# No KBD shortcut in Emacs by default.
map <c-g><c-p> togglePinTab

# Not implemented in Emacs.
# Similar to `buff-move(left|right)`.
# See package: <http://bit.ly/Z1ZXYg>
# Also similar to: `(backward|forward)-word`
# However, this uses capitals w/ the shift key.
map <a-B> moveTabLeft
map <a-F> moveTabRight

# Similar to Emacs help commands.
map <c-h> showHelp
```
