# LOTTO24 / tickets-example

Example for integrating LOTTO24 tickets with partners

## How to add a LOTTO24 ticket to your page

To integrate a ticket with your page, first define an HTML element that will be replaced when the ticket is mounted:

```HTML
<div id="ticket-placeholder"></div>
```

Add this script to your page:

```HTML
 <script src="https://dbg-assets.lotto24.de/external/stable/external.min.js"></script>
 ```

After the external-tickets script has been loaded, call the `ExternalTicket.mount(...)` method:

```javascript
const eventsHandler = (event, data) => {
    // do something with event, data
    console.log(event, data)
};

ExternalTicket.mount({
    selector: '#ticket-placeholder',
    gameId: 'dbg.lotto.normal',
    site: 'lotto24_de',
    query: 'ticketQuicktipp=true&lotto_numberOfBlocks=5',
    submitTarget: 'blank',
    submitTrackingParams: { bar: 'baz' },
    customCss: ' body { color: red; }',
    eventsHandler
});
```