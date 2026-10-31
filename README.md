# REAPER Plugins

A collection of custom JSFX audio plugins by Michael Grafl for REAPER.
Plugin source files live in `effects/`; additional plugins can be added there.

## Plugins

### 2-Band Splitter LR4

[Source](effects/2-Band%20Splitter%20LR4.jsfx)

A stereo, two-band Linkwitz–Riley fourth-order crossover with 24 dB/octave
slopes. Adapted from LOSER's splitter, reducing the original
three bands to two and replacing the filters with cascaded Butterworth biquads.

- One crossover control: 20–20,000 Hz, default 1,000 Hz.
- The effective frequency is limited to 49% of the sample rate.
- Low band: output channels 1–2 (left/right).
- High band: output channels 3–4 (left/right).

## Installation

1. In REAPER, choose **Options → Show REAPER resource path in explorer/finder**.
2. Copy the desired `.jsfx` files from `effects/` into the resource folder's
   `Effects` directory, optionally inside a `Michael Grafl` subfolder.
3. Refresh the FX browser or restart REAPER, then search for **2-Band Splitter LR4**.

If an older copy is already installed, replace that copy rather than installing
another copy alongside it. Keep its existing filename if saved projects refer
to it. The earlier extensionless `2-Band Splitter LR4` and `grafl` files contained
the same plugin.

## Using the crossover

1. Set the track to at least **4 channels** in its routing window.
2. Insert the splitter and set the crossover frequency.
3. Use downstream FX pin routing or track sends to process channels 1–2 and
   3–4 separately.
4. To recombine the bands, route both stereo pairs to the same stereo output
   using sends or a channel mixer. The splitter itself does not mix them back
   together. Listening only to channels 1–2 gives you only the low band.

The unprocessed bands sum to a flat magnitude response, with phase rotation;
their sum is not sample-identical to the dry input. Crossover changes are not
smoothed, so abrupt changes may produce audible artifacts.

## Attribution and source notice

The crossover is based on the 2006 splitter by LOSER. Its
original source notice is retained in the plugin and in [LICENSE.txt](LICENSE.txt).
No replacement license is applied to that code. Future plugins should include
their own applicable notices.

The first Git commit preserves the original source before the metadata and
formatting cleanup. That cleanup does not change the DSP expressions.
