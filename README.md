# makeaqr

Render a QR code for any URL, ready to print or download, from a single static page.

```
https://makeaqr.publica.la/?url=https%3A%2F%2Fexample.com&name=Example
```

## Query parameters

| Parameter | Effect |
| --- | --- |
| `url` | The value encoded in the QR code. Encode it once with `encodeURIComponent()`. A value encoded twice also works, because the page decodes it again when it still starts with a scheme followed by `%3A`. |
| `name` | A heading shown above the QR code. It is also the downloaded file name. |
| `print_copy` | The label of the print button. |
| `download_copy` | The label of the download button. |
| `show_action_buttons` | Pass `false` to hide both buttons. |
| `max_width`, `max_height` | Limit the QR code to this many pixels and scale the canvas to fit, so it is not cropped inside an iframe. |

## Hosting

Every push to `master` deploys `index.html` to two hosts. There is no build step.

- `makeaqr.publica.la` on Cloudflare Pages. Publica.la apps embed this host.
- `makeaqr.com` on Vercel.

Each branch also gets a preview deployment on both hosts.
