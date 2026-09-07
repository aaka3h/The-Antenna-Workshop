# The Antenna Workshop

A browser-based collection of 12 DIY antenna guides, with materials lists, example dimensions, build steps, and inline SVG diagrams. The project is a single HTML page with an optional Google Gemini chat interface.

[Open the website](https://aaka3h.github.io/The-Antenna-Workshop/)

## Antenna guides

| Guide | Topics covered |
| --- | --- |
| [Half-wave dipole](https://aaka3h.github.io/The-Antenna-Workshop/#dipole) | Wire elements, feed point, and frequency-based sizing |
| [Ground-plane vertical](https://aaka3h.github.io/The-Antenna-Workshop/#groundplane) | Vertical radiator and radial construction |
| [Cantenna](https://aaka3h.github.io/The-Antenna-Workshop/#cantenna) | Tin-can antenna for 2.4 GHz WiFi |
| [Yagi-Uda](https://aaka3h.github.io/The-Antenna-Workshop/#yagi) | Driven element, reflector, and directors |
| [J-pole](https://aaka3h.github.io/The-Antenna-Workshop/#jpole) | A 145 MHz construction example |
| [Magnetic loop](https://aaka3h.github.io/The-Antenna-Workshop/#loop) | Loop construction, coupling, and tuning |
| [Parabolic dish](https://aaka3h.github.io/The-Antenna-Workshop/#parabolic) | Dish and feed assembly |
| [Bi-quad](https://aaka3h.github.io/The-Antenna-Workshop/#biquad) | A 2.45 GHz WiFi construction example |
| [Beverage wire](https://aaka3h.github.io/The-Antenna-Workshop/#beverage) | Long-wire receiving antenna construction |
| [Cubical quad](https://aaka3h.github.io/The-Antenna-Workshop/#quad) | A 28 MHz construction example |
| [Helical](https://aaka3h.github.io/The-Antenna-Workshop/#helical) | Helix construction and circular polarization |
| [Discone](https://aaka3h.github.io/The-Antenna-Workshop/#discone) | Disc, cone, and scanner-antenna construction |

Use the sidebar to jump between guides. Dimensions are examples for the frequencies named in each guide; they are not a guarantee of bandwidth or performance for every build.

## Run locally

Clone the repository:

```sh
git clone https://github.com/aaka3h/The-Antenna-Workshop.git
cd The-Antenna-Workshop
```

Open `index.html` in a modern browser. No package installation or build step is required.

For a local HTTP preview, if Python 3 is installed:

```sh
python -m http.server 8000 --bind 127.0.0.1
```

Then open [http://localhost:8000](http://localhost:8000). On systems where Python 3 is named `python3`, use that command instead.

The guides and diagrams are included in `index.html`. The page loads typography from Google Fonts; the AI assistant also requires an internet connection.

## Optional AI assistant

The **Ask AI** panel is designed to answer antenna questions, suggest materials, discuss dimensions, and display text or SVG diagrams returned by Gemini.

**Current limitation:** `index.html` still selects `gemini-1.5-flash-latest`. Google [shut down the Gemini 1.5 model family](https://ai.google.dev/gemini-api/docs/changelog#september-29-2025) on September 29, 2025. The assistant needs an update to a supported model and a compatibility check before it can be relied on. The static guides work independently of the assistant.

The existing chat interface works as follows once its API integration is updated:

1. Obtain your own key from [Google AI Studio](https://aistudio.google.com/app/apikey).
2. Select **Ask AI**, paste the key, and select **Save & Start Chatting**. The page sends a test request before saving it.
3. Enter a question or choose a suggested prompt. Press **Enter** to send, or **Shift+Enter** for a new line.
4. Use the gear button to change the key or the reset button to clear the conversation.

The key is saved in this browser's `localStorage` under `antenna_gemini_key`. Requests, including the conversation, go directly from the browser to Google's Gemini API. There is no application backend, and the chat is not processed entirely on your device. Clearing the conversation does not delete the saved key; clear the site's browser storage to remove it.

API access, quotas, and any charges depend on your Google project and selected model. See Google's [rate limits](https://ai.google.dev/gemini-api/docs/rate-limits) and [pricing](https://ai.google.dev/gemini-api/docs/pricing) for current details.

## Project structure

```text
index.html                         Page content, styles, diagrams, and JavaScript
README.md                          Project overview and setup
.github/workflows/jekyll-docker.yml Jekyll build workflow
```

The site uses plain HTML, CSS, and JavaScript, with no JavaScript framework or package dependencies. Local viewing does not require the Jekyll workflow.

## Contributing

Corrections, clearer diagrams, and additional antenna guides are welcome through issues and pull requests. Include the target frequency and the reasoning or reference behind changes to dimensions or construction advice.

## License

The project is described as MIT-licensed. A separate `LICENSE` file is not currently included in the repository.
