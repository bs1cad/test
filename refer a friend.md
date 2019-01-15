## Refer Friend

**category**|**action**|**label**|**trigger**
:-----:|:-----:|:-----:|:-----:
refer a friend|accepted referral|'went to', 'came back'|user who has been referred goes to or comes back from the referral modal
refer a friend|referred friend|'went to', 'came back'|user who wants to refer goes to or comes back from the referral modal


#### Refer a friend events - JS
##### referred friend
```JavaScript
window.snowplow('trackSelfDescribingEvent',
{
    schema: 'iglu:com.babylonhealth/referral/jsonschema/1-0-0',
    data: {
      provider: provider
    }
  [
  }, 
  {
    schema: 'iglu:com.babylonhealth/generic_events/jsonschema/1-0-0',
    data: {
    category: 'refer a friend',
    action: 'referred friend',
    label: 'went to'
  }}]
  );
```
##### referred friend return
```JavaScript
window.snowplow('trackSelfDescribingEvent',
{
    schema: 'iglu:com.babylonhealth/referral/jsonschema/1-0-0',
    data: {
      provider: provider
    }
  [
  {
    schema: 'iglu:com.babylonhealth/generic_events/jsonschema/1-0-0',
    data: {
    category: 'refer a friend',
    action: 'referred friend',
    label: 'came back'
  }}]
  );
```
##### accepted referral
```JavaScript
window.snowplow('trackSelfDescribingEvent',
{
    schema: 'iglu:com.babylonhealth/referral/jsonschema/1-0-0',
    data: {
      provider: provider
    }
  [
  {
    schema: 'iglu:com.babylonhealth/generic_events/jsonschema/1-0-0',
    data: {
    category: 'refer a friend',
    action: 'accepted referral',
    label: 'went to'
  }}]
  );
```
##### accepted referral return
```JavaScript
window.snowplow('trackSelfDescribingEvent',
{
    schema: 'iglu:com.babylonhealth/referral/jsonschema/1-0-0',
    data: {
      provider: provider
    }
  [
  {
    schema: 'iglu:com.babylonhealth/generic_events/jsonschema/1-0-0',
    data: {
    category: 'refer a friend',
    action: 'accepted referral',
    label: 'came back'
  }}]
  );
```
#### Referral events - Android
##### referred friend
```java
Map<String, Object> genericEvent = new HashMap<>();
genericEvent.put("category", "refer a friend");
genericEvent.put("action", "referred friend");
genericEvent.put("label", "went to");

SelfDescribingJson genericEntity = new SelfDescribingJson("iglu:com.babylonhealth/generic_events/jsonschema/1-0-0", genericEvent);

List<SelfDescribingJson> entities = new ArrayList<>();
entities.add(genericEntity);

Map<String, Object> referralEvent = new HashMap<>();
referralEvent.put("provider", provider)

SelfDescribingJson eventData = new SelfDescribingJson("iglu:com.babylonhealth/referral/jsonschema/1-0-0", referralEvent);

Tracker.track(SelfDescribing.builder()
    .eventData(eventData)
    .customContext(entities)
    .build());
```
##### referred friend return
```java
Map<String, Object> genericEvent = new HashMap<>();
genericEvent.put("category", "refer a friend");
genericEvent.put("action", "referred friend");
genericEvent.put("label", "came back");

SelfDescribingJson genericEntity = new SelfDescribingJson("iglu:com.babylonhealth/generic_events/jsonschema/1-0-0", genericEvent);

List<SelfDescribingJson> entities = new ArrayList<>();
entities.add(genericEntity);

Map<String, Object> referralEvent = new HashMap<>();
referralEvent.put("provider", provider)

SelfDescribingJson eventData = new SelfDescribingJson("iglu:com.babylonhealth/referral/jsonschema/1-0-0", referralEvent);

Tracker.track(SelfDescribing.builder()
    .eventData(eventData)
    .customContext(entities)
    .build());
```
##### accepted referral
```java
Map<String, Object> genericEvent = new HashMap<>();
genericEvent.put("category", "refer a friend");
genericEvent.put("action", "accepted referral");
genericEvent.put("label", "went to");

SelfDescribingJson genericEntity = new SelfDescribingJson("iglu:com.babylonhealth/generic_events/jsonschema/1-0-0", genericEvent);

List<SelfDescribingJson> entities = new ArrayList<>();
entities.add(genericEntity);

Map<String, Object> referralEvent = new HashMap<>();
referralEvent.put("provider", provider)

SelfDescribingJson eventData = new SelfDescribingJson("iglu:com.babylonhealth/referral/jsonschema/1-0-0", referralEvent);

Tracker.track(SelfDescribing.builder()
    .eventData(eventData)
    .customContext(entities)
    .build());
```
##### accepted referral return
```java
Map<String, Object> genericEvent = new HashMap<>();
genericEvent.put("category", "refer a friend");
genericEvent.put("action", "accepted referral");
genericEvent.put("label", "came back");

SelfDescribingJson genericEntity = new SelfDescribingJson("iglu:com.babylonhealth/generic_events/jsonschema/1-0-0", genericEvent);

List<SelfDescribingJson> entities = new ArrayList<>();
entities.add(genericEntity);

Map<String, Object> referralEvent = new HashMap<>();
referralEvent.put("provider", provider)

SelfDescribingJson eventData = new SelfDescribingJson("iglu:com.babylonhealth/referral/jsonschema/1-0-0", referralEvent);

Tracker.track(SelfDescribing.builder()
    .eventData(eventData)
    .customContext(entities)
    .build());
```
#### Referral events - iOS
##### referred friend
```objective-c
NSDictionary *genericEvent = @{
                         @"schema":@"iglu:com.babylonhealth/generic_event/jsonschema/1-0-0",
                         @"data": @{
                                 @"category": @"refer a friend",
                                 @"action": @"referred friend",
                                 @"label": @went to
                                 }
                        };

NSDictionary *referralEvent = @{
                        @"data": @{
                                @"provider": @provider
                                }
                        };

SPSelfDescribingJson *sdj = [[SPSelfDescribingJson alloc] initWithSchema:@"iglu:com.babylonhealth/referral/jsonschema/1-0-0"
                                                                  andData:referralEvent];

SPUnstructured *event = [SPUnstructured build:^(id<SPUnstructuredBuilder> builder) {
  [builder setEventData:sdj];
  [builder setContexts:[NSMutableArray arrayWithArray:@[genericEvent]]];
}];

[tracker trackUnstructuredEvent:event];
```
##### referred friend return
```objective-c
NSDictionary *genericEvent = @{
                         @"schema":@"iglu:com.babylonhealth/generic_event/jsonschema/1-0-0",
                         @"data": @{
                                 @"category": @"refer a friend",
                                 @"action": @"referred friend",
                                 @"label": @came back
                                 }
                        };

NSDictionary *referralEvent = @{
                        @"data": @{
                                @"provider": @provider
                                }
                        };

SPSelfDescribingJson *sdj = [[SPSelfDescribingJson alloc] initWithSchema:@"iglu:com.babylonhealth/referral/jsonschema/1-0-0"
                                                                  andData:referralEvent];

SPUnstructured *event = [SPUnstructured build:^(id<SPUnstructuredBuilder> builder) {
  [builder setEventData:sdj];
  [builder setContexts:[NSMutableArray arrayWithArray:@[genericEvent]]];
}];

[tracker trackUnstructuredEvent:event];
```
##### accepted referral
```objective-c
NSDictionary *genericEvent = @{
                         @"schema":@"iglu:com.babylonhealth/generic_event/jsonschema/1-0-0",
                         @"data": @{
                                 @"category": @"refer a friend",
                                 @"action": @"accepted referral",
                                 @"label": @went to
                                 }
                        };

NSDictionary *referralEvent = @{
                        @"data": @{
                                @"provider": @provider
                                }
                        };

SPSelfDescribingJson *sdj = [[SPSelfDescribingJson alloc] initWithSchema:@"iglu:com.babylonhealth/referral/jsonschema/1-0-0"
                                                                  andData:referralEvent];

SPUnstructured *event = [SPUnstructured build:^(id<SPUnstructuredBuilder> builder) {
  [builder setEventData:sdj];
  [builder setContexts:[NSMutableArray arrayWithArray:@[genericEvent]]];
}];

[tracker trackUnstructuredEvent:event];
```
##### accepted referral
```objective-c
NSDictionary *genericEvent = @{
                         @"schema":@"iglu:com.babylonhealth/generic_event/jsonschema/1-0-0",
                         @"data": @{
                                 @"category": @"refer a friend",
                                 @"action": @"accepted referral",
                                 @"label": @came back
                                 }
                        };

NSDictionary *referralEvent = @{
                        @"data": @{
                                @"provider": @provider
                                }
                        };

SPSelfDescribingJson *sdj = [[SPSelfDescribingJson alloc] initWithSchema:@"iglu:com.babylonhealth/referral/jsonschema/1-0-0"
                                                                  andData:referralEvent];

SPUnstructured *event = [SPUnstructured build:^(id<SPUnstructuredBuilder> builder) {
  [builder setEventData:sdj];
  [builder setContexts:[NSMutableArray arrayWithArray:@[genericEvent]]];
}];

[tracker trackUnstructuredEvent:event];
```
## Parameter definitions
These schema simply define the set of parameters we append to some of the event classes above

#### referral schema
**parameter**|**definition**
:-----:|:-----:
provider|provider used for referral modal. Mention Me for example
