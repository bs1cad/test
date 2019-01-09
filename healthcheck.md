## Healthcheck

The example below is for users who choose nutrition. A complete list of possible event labels can be found [here](https://github.com/bs1cad/test/blob/master/healthcheck%20Event%20label.md)

**category**|**action**|**label**|**trigger**
:-----:|:-----:|:-----:|:-----:
healthcheck|started healthcheck|nutrition onboarding *or* nutrition twin *or* nutrition retake|user starts healthcheck option from welcome screen *or* digital twin *or* by retaking a completed assessment
healthcheck|completed healthcheck|nutrition onboarding *or* nutrition twin *or* nutrition retake|user completes healthcheck option from welcome screen *or* digital twin *or* by retaking a completed assessment


#### Healthcheck events - JS
##### started healthcheck onboarding
```JavaScript
window.snowplow('trackSelfDescribingEvent',
  {
    schema: 'iglu:com.babylonhealth/generic_events/jsonschema/1-0-0',
    data: {
    category: 'healthcheck',
    action: 'started healthcheck',
    label: 'nutrition onboarding'
  }}
  );
```
##### completed healthcheck onboarding
```JavaScript
window.snowplow('trackSelfDescribingEvent',
  {
    schema: 'iglu:com.babylonhealth/generic_events/jsonschema/1-0-0',
    data: {
    category: 'healthcheck',
    action: 'completed healthcheck',
    label: 'nutrition onboarding'
  }}
  );
```
##### started healthcheck twin
```JavaScript
window.snowplow('trackSelfDescribingEvent',
  {
    schema: 'iglu:com.babylonhealth/generic_events/jsonschema/1-0-0',
    data: {
    category: 'healthcheck',
    action: 'started healthcheck',
    label: 'nutrition twin'
  }}
  );
  ```
  ##### completed healthcheck twin
```JavaScript
window.snowplow('trackSelfDescribingEvent',
  {
    schema: 'iglu:com.babylonhealth/generic_events/jsonschema/1-0-0',
    data: {
    category: 'healthcheck',
    action: 'completed healthcheck',
    label: 'nutrition twin'
  }}
  );
  ```
  ##### start retake healthcheck
```JavaScript
window.snowplow('trackSelfDescribingEvent',
  {
    schema: 'iglu:com.babylonhealth/generic_events/jsonschema/1-0-0',
    data: {
    category: 'healthcheck',
    action: 'start healthcheck',
    label: 'nutrition retake'
  }}
  );
  ```
   ##### complete retake healthcheck
```JavaScript
window.snowplow('trackSelfDescribingEvent',
  {
    schema: 'iglu:com.babylonhealth/generic_events/jsonschema/1-0-0',
    data: {
    category: 'healthcheck',
    action: 'complete healthcheck',
    label: 'nutrition retake'
  }}
  );
```
#### healthcheck events - Android
##### started healthcheck onboarding
```java
Map<String, Object> genericEvent = new HashMap<>();
genericEvent.put("category", "healthcheck");
genericEvent.put("action", "started healthcheck");
genericEvent.put("label", "nutrition onboarding);

SelfDescribingJson genericEntity = new SelfDescribingJson("iglu:com.babylonhealth/generic_events/jsonschema/1-0-0", genericEvent);

List<SelfDescribingJson> entities = new ArrayList<>();
entities.add(genericEntity);

Map<String, Object> healthcheckEvent = new HashMap<>();
healthcheckEvent.put("chatId", chatId)

SelfDescribingJson eventData = new SelfDescribingJson("iglu:com.babylonhealth/healthcheck/jsonschema/1-0-0", chatId);

Tracker.track(SelfDescribing.builder()
    .eventData(eventData)
    .customContext(entities)
    .build());
```
##### completed healthcheck onboarding
```java
Map<String, Object> genericEvent = new HashMap<>();
genericEvent.put("category", "healthcheck");
genericEvent.put("action", "completed healthcheck");
genericEvent.put("label", "nutrition onboarding);

SelfDescribingJson genericEntity = new SelfDescribingJson("iglu:com.babylonhealth/generic_events/jsonschema/1-0-0", genericEvent);

List<SelfDescribingJson> entities = new ArrayList<>();
entities.add(genericEntity);

Map<String, Object> healthcheckEvent = new HashMap<>();
healthcheckEvent.put("chatId", chatId)

SelfDescribingJson eventData = new SelfDescribingJson("iglu:com.babylonhealth/healthcheck/jsonschema/1-0-0", chatId);

Tracker.track(SelfDescribing.builder()
    .eventData(eventData)
    .customContext(entities)
    .build());
```
##### started healthcheck twin
```java
Map<String, Object> genericEvent = new HashMap<>();
genericEvent.put("category", "healthcheck");
genericEvent.put("action", "started healthcheck");
genericEvent.put("label", "nutrition twin);

SelfDescribingJson genericEntity = new SelfDescribingJson("iglu:com.babylonhealth/generic_events/jsonschema/1-0-0", genericEvent);

List<SelfDescribingJson> entities = new ArrayList<>();
entities.add(genericEntity);

Map<String, Object> healthcheckEvent = new HashMap<>();
healthcheckEvent.put("chatId", chatId)

SelfDescribingJson eventData = new SelfDescribingJson("iglu:com.babylonhealth/healthcheck/jsonschema/1-0-0", chatId);

Tracker.track(SelfDescribing.builder()
    .eventData(eventData)
    .customContext(entities)
    .build());
```
##### completed healthcheck twin
```java
Map<String, Object> genericEvent = new HashMap<>();
genericEvent.put("category", "healthcheck");
genericEvent.put("action", "completed healthcheck");
genericEvent.put("label", "nutrition twin);

SelfDescribingJson genericEntity = new SelfDescribingJson("iglu:com.babylonhealth/generic_events/jsonschema/1-0-0", genericEvent);

List<SelfDescribingJson> entities = new ArrayList<>();
entities.add(genericEntity);

Map<String, Object> healthcheckEvent = new HashMap<>();
healthcheckEvent.put("chatId", chatId)

SelfDescribingJson eventData = new SelfDescribingJson("iglu:com.babylonhealth/healthcheck/jsonschema/1-0-0", chatId);

Tracker.track(SelfDescribing.builder()
    .eventData(eventData)
    .customContext(entities)
    .build());
```
##### started retake healthcheck
```java
Map<String, Object> genericEvent = new HashMap<>();
genericEvent.put("category", "healthcheck");
genericEvent.put("action", "started healthcheck");
genericEvent.put("label", "nutrition retake);

SelfDescribingJson genericEntity = new SelfDescribingJson("iglu:com.babylonhealth/generic_events/jsonschema/1-0-0", genericEvent);

List<SelfDescribingJson> entities = new ArrayList<>();
entities.add(genericEntity);

Map<String, Object> healthcheckEvent = new HashMap<>();
healthcheckEvent.put("chatId", chatId)

SelfDescribingJson eventData = new SelfDescribingJson("iglu:com.babylonhealth/healthcheck/jsonschema/1-0-0", chatId);

Tracker.track(SelfDescribing.builder()
    .eventData(eventData)
    .customContext(entities)
    .build());
```
##### completed retake healthcheck 
```java
Map<String, Object> genericEvent = new HashMap<>();
genericEvent.put("category", "healthcheck");
genericEvent.put("action", "completed healthcheck");
genericEvent.put("label", "nutrition retake);

SelfDescribingJson genericEntity = new SelfDescribingJson("iglu:com.babylonhealth/generic_events/jsonschema/1-0-0", genericEvent);

List<SelfDescribingJson> entities = new ArrayList<>();
entities.add(genericEntity);

Map<String, Object> healthcheckEvent = new HashMap<>();
healthcheckEvent.put("chatId", chatId)

SelfDescribingJson eventData = new SelfDescribingJson("iglu:com.babylonhealth/healthcheck/jsonschema/1-0-0", chatId);

Tracker.track(SelfDescribing.builder()
    .eventData(eventData)
    .customContext(entities)
    .build());
```
#### Healthcheck events - iOS
##### started healthcheck onboarding
```objective-c
NSDictionary *genericEvent = @{
                         @"schema":@"iglu:com.babylonhealth/generic_event/jsonschema/1-0-0",
                         @"data": @{
                                 @"category": @"healthcheck",
                                 @"action": @"started healthcheck",
                                 @"label": @"nutrition onboarding"
                                 }
                        };

NSDictionary *healthcheckEvent = @{
                        @"data": @{
                                @"chatId": @chatId
                                }
                        };

SPSelfDescribingJson *sdj = [[SPSelfDescribingJson alloc] initWithSchema:@"iglu:com.babylonhealth/healthcheck/jsonschema/1-0-0"
                                                                  andData:healthcheckEvent];

SPUnstructured *event = [SPUnstructured build:^(id<SPUnstructuredBuilder> builder) {
  [builder setEventData:sdj];
  [builder setContexts:[NSMutableArray arrayWithArray:@[genericEvent]]];
}];

[tracker trackUnstructuredEvent:event];
```
##### completed healthcheck onboarding
```objective-c
NSDictionary *genericEvent = @{
                         @"schema":@"iglu:com.babylonhealth/generic_event/jsonschema/1-0-0",
                         @"data": @{
                                 @"category": @"healthcheck",
                                 @"action": @"completed healthcheck",
                                 @"label": @"nutrition onboarding"
                                 }
                        };

NSDictionary *healthcheckEvent = @{
                        @"data": @{
                                @"chatId": @chatId
                                }
                        };

SPSelfDescribingJson *sdj = [[SPSelfDescribingJson alloc] initWithSchema:@"iglu:com.babylonhealth/healthcheck/jsonschema/1-0-0"
                                                                  andData:healthcheckEvent];

SPUnstructured *event = [SPUnstructured build:^(id<SPUnstructuredBuilder> builder) {
  [builder setEventData:sdj];
  [builder setContexts:[NSMutableArray arrayWithArray:@[genericEvent]]];
}];

[tracker trackUnstructuredEvent:event];
```
##### started healthcheck twin
```objective-c
NSDictionary *genericEvent = @{
                         @"schema":@"iglu:com.babylonhealth/generic_event/jsonschema/1-0-0",
                         @"data": @{
                                 @"category": @"healthcheck",
                                 @"action": @"started healthcheck",
                                 @"label": @"nutrition twin"
                                 }
                        };

NSDictionary *healthcheckEvent = @{
                        @"data": @{
                                @"chatId": @chatId
                                }
                        };

SPSelfDescribingJson *sdj = [[SPSelfDescribingJson alloc] initWithSchema:@"iglu:com.babylonhealth/healthcheck/jsonschema/1-0-0"
                                                                  andData:healthcheckEvent];

SPUnstructured *event = [SPUnstructured build:^(id<SPUnstructuredBuilder> builder) {
  [builder setEventData:sdj];
  [builder setContexts:[NSMutableArray arrayWithArray:@[genericEvent]]];
}];

[tracker trackUnstructuredEvent:event];
```
##### completed healthcheck twin
```objective-c
NSDictionary *genericEvent = @{
                         @"schema":@"iglu:com.babylonhealth/generic_event/jsonschema/1-0-0",
                         @"data": @{
                                 @"category": @"healthcheck",
                                 @"action": @"completed healthcheck",
                                 @"label": @"nutrition twin"
                                 }
                        };

NSDictionary *healthcheckEvent = @{
                        @"data": @{
                                @"chatId": @chatId
                                }
                        };

SPSelfDescribingJson *sdj = [[SPSelfDescribingJson alloc] initWithSchema:@"iglu:com.babylonhealth/healthcheck/jsonschema/1-0-0"
                                                                  andData:healthcheckEvent];

SPUnstructured *event = [SPUnstructured build:^(id<SPUnstructuredBuilder> builder) {
  [builder setEventData:sdj];
  [builder setContexts:[NSMutableArray arrayWithArray:@[genericEvent]]];
}];

[tracker trackUnstructuredEvent:event];
```
##### started retake healthcheck
```objective-c
NSDictionary *genericEvent = @{
                         @"schema":@"iglu:com.babylonhealth/generic_event/jsonschema/1-0-0",
                         @"data": @{
                                 @"category": @"healthcheck",
                                 @"action": @"started healthcheck",
                                 @"label": @"nutrition retake"
                                 }
                        };

NSDictionary *healthcheckEvent = @{
                        @"data": @{
                                @"chatId": @chatId
                                }
                        };

SPSelfDescribingJson *sdj = [[SPSelfDescribingJson alloc] initWithSchema:@"iglu:com.babylonhealth/healthcheck/jsonschema/1-0-0"
                                                                  andData:healthcheckEvent];

SPUnstructured *event = [SPUnstructured build:^(id<SPUnstructuredBuilder> builder) {
  [builder setEventData:sdj];
  [builder setContexts:[NSMutableArray arrayWithArray:@[genericEvent]]];
}];

[tracker trackUnstructuredEvent:event];
```
##### completed retake healthcheck
```objective-c
NSDictionary *genericEvent = @{
                         @"schema":@"iglu:com.babylonhealth/generic_event/jsonschema/1-0-0",
                         @"data": @{
                                 @"category": @"healthcheck",
                                 @"action": @"completed healthcheck",
                                 @"label": @"nutrition retake"
                                 }
                        };

NSDictionary *healthcheckEvent = @{
                        @"data": @{
                                @"chatId": @chatId
                                }
                        };

SPSelfDescribingJson *sdj = [[SPSelfDescribingJson alloc] initWithSchema:@"iglu:com.babylonhealth/healthcheck/jsonschema/1-0-0"
                                                                  andData:healthcheckEvent];

SPUnstructured *event = [SPUnstructured build:^(id<SPUnstructuredBuilder> builder) {
  [builder setEventData:sdj];
  [builder setContexts:[NSMutableArray arrayWithArray:@[genericEvent]]];
}];

[tracker trackUnstructuredEvent:event];
```
