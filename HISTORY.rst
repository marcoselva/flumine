.. :changelog:

Release History
---------------

1.14.7 (2020-11-14)
+++++++++++++++++++

**Improvements**

- Minor bug on initial init with calculate_traded func

1.14.6 (2020-11-13)
+++++++++++++++++++

**Improvements**

- Refactor on calculate_traded func (15% speed increase)

**Bug Fixes**

- Refactoring create_order_from_current, so that it is not dependent on the '-' separator (@jsphon)

1.14.5 (2020-11-11)
+++++++++++++++++++

**Improvements**

- Docs cleanup

**Bug Fixes**

- #318 process customer order ref
- Rounding on order properties

1.14.4 (2020-11-05)
+++++++++++++++++++

**Improvements**

- #310 typing update and bool return added on stream
- add min_bet_validation flag to prevent control checking min size

**Bug Fixes**

- filters out violated orders from being used to calculate the selection exposure (@lunswor)
- handle simulated cancel when size reduction is larger than size remaining
- pass correct size into create replace order based on api response
- #314 Calculates size_remaining from size and size_matched when not set from placeResponse

1.14.3 (2020-11-02)
+++++++++++++++++++

**Improvements**

- size reduction bug

1.14.2 (2020-11-02)
+++++++++++++++++++

**Improvements**

- _process_cleared_orders called on market closure when backtesting / paper trading
- size reduction handling added to simulated execution on cancel
- Add py3.9 actions test

**Libraries**

- betfairlightweight upgraded to 2.10.0 (exchange stream api release 10/11/20)

1.14.1 (2020-10-29)
+++++++++++++++++++

**Improvements**

- #297 add violation msg to order on violation
- Graceful worker shutdown
- Terminate worker example added

**Libraries**

- betfairlightweight upgraded to 2.9.2
- python-json-logger upgraded to 2.0.1

1.14.0 (2020-10-12)
+++++++++++++++++++

**Improvements**

- Prevent MarketBook latency logging when update is from a snap

**Bug Fixes**

- #291 Bug in calculated_unmatched_exposure func

**Libraries**

- betfairlightweight upgraded to 2.9.0 (#248 memory leak)

1.13.1 (2020-10-08)
+++++++++++++++++++

**Improvements**

- Updates the pricerecorder example method parameters (@lunswor)
- #248 Remove runner_context from strategy on market remove
- #287 order separator (jsphon)

1.13.0 (2020-10-05)
+++++++++++++++++++

**Improvements**

- #270 strategy exposure improvements on trading control

**Bug Fixes**

- Handle unhandled exceptions in execution
- Replace now fixed (regression on removal of `order_package.market`
- Backtest process orders now called before strategy calls *impacts backtesting profit*

**Libraries**

- python-json-logger upgraded to 2.0.0

1.12.3 (2020-09-28)
+++++++++++++++++++

**Bug Fixes**

- Missing book / bet_delay in live fix

1.12.2 (2020-09-28)
+++++++++++++++++++

**Bug Fixes**

- #248 completely remove circular reference to market->blotter
- Correct market closure when recording data (raw)

1.12.1 (2020-09-21)
+++++++++++++++++++

**Bug Fixes**

- #275 Laying Limit Orders, Persistence Type MARKET_ON_CLOSE (@jsphon)
- PR added to actions

1.12.0 (2020-09-14)
+++++++++++++++++++

**Improvements**

- #269 latency warning added

**Bug Fixes**

- #248 addition of weakref to try and break circular reference (@synapticarbors) + deletion of each event

**Libraries**

- betfairlightweight upgraded to 2.8.0 (orjson)
- black updated to 20.8b1

1.11.2 (2020-08-28)
+++++++++++++++++++

**Improvements**

- Minor refactor and test improvements on FlumineBacktest
- Tennis/inplayservice worker example added

**Bug Fixes**

- Validates runner is active on placeOrder when simulating (@lunswor)
- Complete.trade moved to when order or trade status updates rather than process.py, previously it was missing any orders that violated when no other orders active

1.11.1 (2020-08-24)
+++++++++++++++++++

**Improvements**

- #187 strategy and trade runner context additions

**Bug Fixes**

- Handling for SP orders on startup
- Bug fix on client control max orders when backtesting

1.11.0 (2020-08-03)
+++++++++++++++++++

**Improvements**

- invested migrated to executable_orders on RunnerContext *breaking change
- Use MarketCatalogue where available for market descriptions
- Create session added, sessions closed and deleted if stale for 200s or more

**Bug Fixes**

- Limit process to limit orders to prevent SP orders from being completed when not + test bug fix

1.10.6 (2020-08-10)
+++++++++++++++++++

**Bug Fixes**

- Prevent closed markets being removed when paper trading
- Fix missing MarketBook from market (closes #FLUMINE-PROD-EE)

1.10.5 (2020-08-04)
+++++++++++++++++++

**Bug Fixes**

- Prevent closed markets being removed when backtesting
- Adds check to check removal_adjustment_factor is not None when processing runner removal (@lunswor)

1.10.4 (2020-08-03)
+++++++++++++++++++

**Improvements**

- updates for bflw 2.7.2

**Libraries**

- betfairlightweight upgraded to 2.7.2

1.10.3 (2020-08-03)
+++++++++++++++++++

**Bug Fixes**

- Handle missing id in raw data (race stream)
- Handle no market passed to market recorder (race stream)

1.10.2 (2020-08-03)
+++++++++++++++++++

**Improvements**

- _process_raw_data refactored to create market objects and call market.closed_market on closure

**Bug Fixes**

- Docs typo (thanks @petercoles)

**Libraries**

- betfairlightweight upgraded to 2.7.1

1.10.1 (2020-07-20)
+++++++++++++++++++

**Bug Fixes**

- Add middleware moved to init, Simulated needs to be the first middleware

1.10.0 (2020-07-20)
+++++++++++++++++++

**Improvements**

- #180 client paper trade now implemented
- #193 initial work on multi client implementation
- #192 simulation improvements with handling on runner removal

1.9.3 (2020-07-17)
+++++++++++++++++++

**Bug Fixes**

- Move remove_markets logic to process_closed_markets (previously not called if no orders)
- Travis remove py3.5

1.9.2 (2020-07-16)
+++++++++++++++++++

**Improvements**

- update_market_notes refactor and move to utils to make patching easier

**Bug Fixes**

- Market.closed now updated when reopened + logging improvements

1.9.1 (2020-07-15)
+++++++++++++++++++

**Improvements**

- #184 package retry on error (limited to 3 with back-off)
- requests.Session now closed and deleted

1.9.0 (2020-07-13)
+++++++++++++++++++

**Improvements**

- #201 requests session kept and reused to reduce latency
- Middleware add/remove market functions added and integrated into Simulated
- Logging improvements

**Libraries**

- betfairlightweight upgraded to 2.6.0

1.8.2 (2020-07-06)
+++++++++++++++++++

**Improvements**

- Previous 'middle' and 'matched' added to simulated

**Bug Fixes**

- Simulated bug fix on when data is not recorded from the beginning
- Client control 'None' bug fix

1.8.1 (2020-06-30)
+++++++++++++++++++

**Bug Fixes**

- Reduce MC count (debugging seg fault)

1.8.0 (2020-06-29)
+++++++++++++++++++

**Improvements**

- Custom historical listener/stream added
- Large order count (per market) optimisations
- #203 client transaction count
- #224 multi market processing

**Bug Fixes**

- #221 RuntimeError: market/order looping

**Libraries**

- betfairlightweight upgraded to 2.5.0

1.7.0 (2020-06-15)
+++++++++++++++++++

**Improvements**

- market_notes added to Trade
- market removed after closed for 3600 seconds
- client.best_price_execution handling added

1.6.8 (2020-06-10)
+++++++++++++++++++

**Improvements**

- Simulated optimisations on matched size/price (@jsphon)

**Libraries**

- betfairlightweight upgraded to 2.4.0

1.6.7 (2020-06-08)
+++++++++++++++++++

**Improvements**

- #185 cleared orders meta implemented
- Order.elapsed_seconds_executable added

1.6.6 (2020-06-08)
+++++++++++++++++++

**Improvements**

- Error handling added to logging control

**Bug Fixes**

- Incorrect event type passed to log_control

1.6.5 (2020-06-08)
+++++++++++++++++++

**Improvements**

- #205 MarketBook publishTime added to simulated.matched / order.execution_complete time added
- Controls error message added
- Info properties improved
- Order/Trade .complete refactored

**Bug Fixes**

- Log order moved to after execution (missing betId)

1.6.4 (2020-06-08)
+++++++++++++++++++

**Improvements**

- Client passed in AccountBalance event
- PublishTime added to order (MarketBook)
- GH Actions fixed

1.6.3 (2020-06-03)
+++++++++++++++++++

**Improvements**

- #178 Client order stream disable/enable
- #179 Info properties

**Bug Fixes**

- #191 missing git config

1.6.2 (2020-06-03)
+++++++++++++++++++

**Improvements**

- #191 Github actions added for testing and deployment

1.6.1 (2020-06-02)
+++++++++++++++++++

**Bug Fixes**

- #195 refactor to prevent RuntimeError

1.6.0 (2020-06-02)
+++++++++++++++++++

**Improvements**

- #175 Update/Replace simulated handling
- Trade context manager added

**Bug Fixes**

- #163 selection exposure improvement
- BetfairExecution replace bugfix

1.5.7 (2020-06-01)
+++++++++++++++++++

**Bug Fixes**

- Sentry uses name in extra so do not override.

1.5.6 (2020-06-01)
+++++++++++++++++++

**Improvements**

- #186 Error handling when calling strategy functions
- Start delay bumped on workers and name changed
- Minor typos / cleanups

1.5.5 (2020-05-29)
+++++++++++++++++++

**Improvements**

- Missing Middleware inheritance
- get_sp added

**Bug Fixes**

- MarketCatalogue missing from Market when logged

1.5.4 (2020-05-22)
+++++++++++++++++++

**Bug Fixes**

- Market close bug

1.5.3 (2020-05-22)
+++++++++++++++++++

**Improvements**

- Market properties added

**Bug Fixes**

- Memory leak in historical stream fixed (queue)
- process_closed_market bug fix in process logic

1.5.2 (2020-05-21)
+++++++++++++++++++

**Bug Fixes**

- pypi bug?

1.5.1 (2020-05-21)
+++++++++++++++++++

**Improvements**

- Worker refactor to make init simpler when adding custom workers

1.5.0 (2020-05-21)
+++++++++++++++++++

**Improvements**

- Logging control added and integrated
- PriceRecorder example added
- Balance polling added
- Cleared Orders/Market polling added
- Trade.notes added
- Middleware moved to flumine level
- SimulatedMiddleware refactored to handle all logic
- Context added to worker functionality

1.4.0 (2020-05-13)
+++++++++++++++++++

**Improvements**

- Simulated execution created (place/cancel only)
- Backtest simulation created and integrated
- patching added, major speed improvements

**Bug Fixes**

- Handicap missing from order
- Client update account details added
- Replace/Update `update_data` fix (now cleared)

**Libraries**

- betfairlightweight upgraded to 2.3.1

1.3.0 (2020-04-28)
+++++++++++++++++++

**Improvements**

- BetfairExecution now live (place/cancel/update/replace)
- Trading and Client controls now live
- Trade/Order logic created and integrated
- OrderPackage created for execution
- Market class created
- process.py created to handle order/trade logic and linking
- Market catalogue worker added
- Blotter created with some initial functions (selection_exposure)
- Strategy runner_context added to handle selection investment
- OrderStream created and integrated

**Bug Fixes**

- Error handling on keep_alive worker added

**Libraries**

- requests added as dependency

1.2.0 (2020-04-06)
+++++++++++++++++++

**Improvements**

- Backtest added and HistoricalStream refactor (single threaded)
- Flumine clients created and integrated
- MarketCatalogue polling worker added

**Libraries**

- betfairlightweight upgraded to 2.3.0

1.1.0 (2020-03-09)
+++++++++++++++++++

**Improvements**

- `context` added to strategy
- `.start` / `.add` refactored to make more sense
- HistoricalStream added and working but will change in the future to not use threads (example added)

**Libraries**

- betfairlightweight upgraded to 2.1.0

1.0.0 (2020-03-02)
+++++++++++++++++++

**Improvements**

- Refactor to trading framework / engine
- Remove recorder/storage engine and replace with 'strategies'
- Market and data streams added
- Background worker class added
- Add docs
- exampleone added

**Libraries**

- betfairlightweight upgraded to 2.0.1
- Add tenacity 5.0.3
- Add python-json-logger 0.1.11

0.9.0 (2020-01-06)
+++++++++++++++++++

**Improvements**

- py3.7/3.8 testing and Black fmt
- main.py update to remove flumine hardcoding
- Remove docker and change to 'main.py' example
- Refactor to local_dir so that it can be overwritten

**Bug Fixes**

- File only loaded if < than 1 line
- FLUMINE_DATA updated to /tmp to prevent permission issues

**Libraries**

- betfairlightweight upgraded to 1.10.4
- Add py3.8 support

0.8.1 (2019-09-30)
+++++++++++++++++++

**Improvements**

- logging improvements (exc_info)
- Python 3.4 removed and 3.7 support added

**Libraries**

- betfairlightweight upgraded to 1.10.3

0.8.0 (2019-09-09)
+++++++++++++++++++

**Improvements**

- black fmt
- _async renamed to `async_` to match bflw
- py3.7 added to travis
- #28 readme update

**Libraries**

- betfairlightweight upgraded to 1.10.2
