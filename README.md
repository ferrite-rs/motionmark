# MotionMark for Servo/Ferrite

This README contains instructions using the benchmarking supplementary material
for the paper _Ferrite: A Judgmental Embedding of Session Types in Rust_.

This is a fork of [MotionMark](https://browserbench.org/MotionMark/)
[WebKit source repository](https://github.com/WebKit/WebKit/tree/e9e8c65749da0a64dacef1e9363f25ff22f3be4a/Websites/browserbench.org/MotionMark1.1).
The fork contains patches to run the benchmark on Servo, for benchmarking
the canvas performance.

## Running Benchmark

The webpage at https://ferrite-rs.github.io/motionmark/developer.html allows us to choose
the specific benchmark suite to run, and the detailed parameters for the
benchmark. To reproduce the benchmarks mentioned in the paper, we
provide the permanent links to each benchmark as follows:

  - **Arc**: https://ferrite-rs.github.io/motionmark/developer.html?test-interval=30&display=minimal&tiles=classic&controller=fixed&frame-rate=50&kalman-process-error=1&kalman-measurement-error=4&time-measurement=performance&suite-name=MotionMark&test-name=CanvasArcs&complexity=500

  - **Paths**: https://ferrite-rs.github.io/motionmark/developer.html?test-interval=30&display=minimal&tiles=classic&controller=fixed&frame-rate=50&kalman-process-error=1&kalman-measurement-error=4&time-measurement=performance&suite-name=MotionMark&test-name=Paths&complexity=1000

  - **Lines**: https://ferrite-rs.github.io/motionmark/developer.html?test-interval=30&display=minimal&tiles=classic&controller=fixed&frame-rate=50&kalman-process-error=1&kalman-measurement-error=4&time-measurement=performance&suite-name=MotionMark&test-name=CanvasLines&complexity=10000

  - **Bouncing clipped rects**: https://ferrite-rs.github.io/motionmark/developer.html?test-interval=30&display=minimal&tiles=classic&controller=fixed&frame-rate=50&kalman-process-error=1&kalman-measurement-error=4&time-measurement=performance&suite-name=Canvassuite&test-name=canvasbouncingclippedrects&complexity=500

  - **Bouncing gradient circles**: https://ferrite-rs.github.io/motionmark/developer.html?test-interval=30&display=minimal&tiles=classic&controller=fixed&frame-rate=50&kalman-process-error=1&kalman-measurement-error=4&time-measurement=performance&suite-name=Canvassuite&test-name=canvasbouncinggradientcircles&complexity=100

  - **Bouncing PNG images**: https://ferrite-rs.github.io/motionmark/developer.html?test-interval=30&display=minimal&tiles=classic&controller=fixed&frame-rate=50&kalman-process-error=1&kalman-measurement-error=4&time-measurement=performance&suite-name=Canvassuite&test-name=canvasbouncingPNGimages&complexity=500

  - **Stroke shapes**: https://ferrite-rs.github.io/motionmark/developer.html?test-interval=30&display=minimal&tiles=classic&controller=fixed&frame-rate=50&kalman-process-error=1&kalman-measurement-error=4&time-measurement=performance&suite-name=Canvassuite&test-name=Strokeshapes&complexity=500

  - **Put/get image data**: https://ferrite-rs.github.io/motionmark/developer.html?test-interval=30&display=minimal&tiles=classic&controller=fixed&frame-rate=50&kalman-process-error=1&kalman-measurement-error=4&time-measurement=performance&suite-name=Canvassuite&test-name=Canvasputgetimagedata&complexity=100

## Running Benchmark on Servo

To run the benchmark on Servo, first build Servo following the
[build instructions](https://github.com/servo/servo#setting-up-your-environment)

```bash
./mach build --release
```

The provide the URL to the built Servo binary, with a fixed resolution
to ensure the that full canvas is rendered. e.g.:

```bash
target/release/servo --resolution 1600x800 https://ferrite-rs.github.io/motionmark/developer.html
```
