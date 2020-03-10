### Changes

* Mithril
    - See changes from v0.2.x @ https://mithril.js.org/migration-v02x.html
    - Kept `m.prop` and `m.withAttr`
    - Actual Promises are used now instead of `m.deferred`
* Component
    - Use new Mithril lifecycle hooks (`component.config` is gone)
        - When implementing your own, you *must* call `super.<hook>(vnode)` to update `this.attrs`
    - `component.render` is gone
* Application
    - New different methods
    - `app.bus` for some event hooking
* Translator
    - Added `app.translator.transText`, automatically extracts text from `translator.trans` output
* Utils
    - Changed `computed` util to require multiple keys to be passed as an array
    - `SubtreeRetainer` now has an `update` method instead of `retain`, and its output is used in `onbeforeupdate` lifecycle hook
    - `Evented` util is now a class instead of an object
    - `formatNumber` now uses `Number.prototype.toLocaleString` with the current application locale, and supports passing an options object (eg. for currency formatting - https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/NumberFormat/resolvedOptions#Description)

#### Forum
* Forum Application
    - Renamed to `Forum`
    - `app.search` is no longer global, extend using `extend`