import { precacheAndRoute } from 'workbox-precaching';
import { registerRoute } from 'workbox-routing';
import { StaleWhileRevalidate } from 'workbox-strategies';

precacheAndRoute(self.__WB_MANIFEST);
registerRoute(
  ({ request }) => request.destination === 'image',
  new StaleWhileRevalidate()
);
