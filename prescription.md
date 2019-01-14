## prescription
**category**|**action**|**label**|**trigger**
:-----:|:-----:|:-----:|:-----:
prescription|started prescription|null|user starts prescription flow
prescription|completed prescription|null|user completes prescription flow


#### Prescription events - JS
##### started prescription
```JavaScript
window.snowplow('trackSelfDescribingEvent',
  {
    schema: 'iglu:com.babylonhealth/prescription/jsonschema/1-0-0',
    data: {
      prescriptionId: appointmentID
    }
  }, 
  [
  {
    schema: 'iglu:com.babylonhealth/generic_events/jsonschema/1-0-0',
    data: {
    category: 'prescription',
    action: 'started prescription',
    label: null
  }}]
  );
```
##### completed prescription
```JavaScript
window.snowplow('trackSelfDescribingEvent',
  {
    schema: 'iglu:com.babylonhealth/prescription/jsonschema/1-0-0',
    data: {
      prescriptionId: appointmentID
    }
  }, 
  [
  {
    schema: 'iglu:com.babylonhealth/generic_events/jsonschema/1-0-0',
    data: {
    category: 'prescription',
    action: 'completed prescription',
    label: null
  }}]
  );
```
#### Prescription events - Android
##### started prescription
```java
Map<String, Object> genericEvent = new HashMap<>();
genericEvent.put("category", "prescription");
genericEvent.put("action", "started prescription");
genericEvent.put("label", null);

SelfDescribingJson genericEntity = new SelfDescribingJson("iglu:com.babylonhealth/generic_events/jsonschema/1-0-0", genericEvent);

List<SelfDescribingJson> entities = new ArrayList<>();
entities.add(genericEntity);

Map<String, Object> prescriptionEvent = new HashMap<>();
prescriptionEvent.put("prescriptionId", prescriptionId)

SelfDescribingJson eventData = new SelfDescribingJson("iglu:com.babylonhealth/prescription/jsonschema/1-0-0", prescriptionEvent);

Tracker.track(SelfDescribing.builder()
    .eventData(eventData)
    .customContext(entities)
    .build());
```
##### completed prescription
```java
Map<String, Object> genericEvent = new HashMap<>();
genericEvent.put("category", "prescription");
genericEvent.put("action", "completed prescription");
genericEvent.put("label", null);

SelfDescribingJson genericEntity = new SelfDescribingJson("iglu:com.babylonhealth/generic_events/jsonschema/1-0-0", genericEvent);

List<SelfDescribingJson> entities = new ArrayList<>();
entities.add(genericEntity);

Map<String, Object> prescriptionEvent = new HashMap<>();
prescriptionEvent.put("prescriptionId", prescriptionId)

SelfDescribingJson eventData = new SelfDescribingJson("iglu:com.babylonhealth/prescription/jsonschema/1-0-0", prescriptionEvent);

Tracker.track(SelfDescribing.builder()
    .eventData(eventData)
    .customContext(entities)
    .build());
```
#### Prescription events - iOS
##### started prescription
```objective-c
NSDictionary *genericEvent = @{
                         @"schema":@"iglu:com.babylonhealth/generic_event/jsonschema/1-0-0",
                         @"data": @{
                                 @"category": @"prescription",
                                 @"action": @"started prescription",
                                 @"label": @null
                                 }
                        };

NSDictionary *prescriptionEvent = @{
                        @"data": @{
                                @"prescriptionId": @prescriptionId
                                }
                        };

SPSelfDescribingJson *sdj = [[SPSelfDescribingJson alloc] initWithSchema:@"iglu:com.babylonhealth/prescription/jsonschema/1-0-0" andData:appointmentEvent];

SPUnstructured *event = [SPUnstructured build:^(id<SPUnstructuredBuilder> builder) {
  [builder setEventData:sdj];
  [builder setContexts:[NSMutableArray arrayWithArray:@[genericEvent]]];
}];

[tracker trackUnstructuredEvent:event];
```
##### completed prescription
```objective-c
NSDictionary *genericEvent = @{
                         @"schema":@"iglu:com.babylonhealth/generic_event/jsonschema/1-0-0",
                         @"data": @{
                                 @"category": @"prescription",
                                 @"action": @"completed prescription",
                                 @"label": @null
                                 }
                        };

NSDictionary *prescriptionEvent = @{
                        @"data": @{
                                @"prescriptionId": @prescriptionId
                                }
                        };

SPSelfDescribingJson *sdj = [[SPSelfDescribingJson alloc] initWithSchema:@"iglu:com.babylonhealth/prescription/jsonschema/1-0-0" andData:appointmentEvent];

SPUnstructured *event = [SPUnstructured build:^(id<SPUnstructuredBuilder> builder) {
  [builder setEventData:sdj];
  [builder setContexts:[NSMutableArray arrayWithArray:@[genericEvent]]];
}];

[tracker trackUnstructuredEvent:event];
```
