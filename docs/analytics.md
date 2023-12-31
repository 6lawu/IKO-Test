# Analytics

Analytics in this app are managed through the [Angulartics2](https://github.com/angulartics/angulartics2) library.

It is already pre-configured to track page views, and provides examples to track events from both TypeScript code and HTML elements.
Here is a quick usage documentation, you can read further information on the official website.

## Registering your provider

Currently, only Google Analytics is fully installed from the starter kit.
Do not worry, this only means you will need to select and import your provider yourself.
Simply follow the instructions detailed in the [official documentation](https://github.com/angulartics/angulartics2#supported-providers).

## Tracking events

### Declarative event tracking

The simplest way to do event tracking is by adding the attributes `angulartics2On`, `angularticsCategory` and `angularticsAction` to an HTML element.
The homepage generated by the starter kit contains one such button.
For reference, here is a UI-framework-agnostic example.

```html
<button angulartics2On="click" angularticsAction="Button clicked" angularticsCategory="UI">Click me to send the current quote as an Analytics event</button>
```

### Using the API

To access the API, inject your provider :

```typescript
constructor(...
            private angulartics2GoogleAnalytics: Angulartics2GoogleAnalytics,
            ...)
```

You may then use the `eventTrack` function:

```typescript
this.angulartics2GoogleAnalytics.eventTrack('Something happened', { category: 'My category' });
this.angulartics2GoogleAnalytics.eventTrack('Something else happened', { category: 'My other category', label: 'My custom label' });
```
