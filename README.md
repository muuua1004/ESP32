If you’re like me—zero programming background, but still really want to mess around with small tech projects—then this video isn’t about teaching you code line by line.
Instead, it’s about giving you a way of thinking: how to go from “I have an idea” to “this thing actually works.”

And if you don’t feel like listening to me talk, no problem—I’ve put the code in the link below. You can just download it and play with it yourself.

First, why an attitude indicator?

Honestly? Mostly because it’s fun.

Riding a motorcycle is sometimes called “flying close to the ground.”
Even though I’m a pretty conservative rider, leaning into corners is unavoidable. And every now and then I get curious—how much am I actually leaning?
Because what it feels like, and what it looks like to others, can be very different.

The second reason is… Seoul.
If you’ve ridden here—or seen my previous riding videos—you know the roads go up and down constantly. They’re rarely flat.

Sometimes while riding, I’d feel like the bike wasn’t accelerating properly.
So I started wondering:
Is this just because I’m going uphill?
Or is there actually something wrong with the bike?

But again, if I’m being honest—this project is still mostly about having fun.

Even though it was “just for fun,” I had never touched an ESP32 board before this.
I assumed building an electronic attitude indicator would be complicated.

That changed when I saw someone else’s video.

I realized, “Wait… this actually doesn’t look that hard.”
And since a development board can be used for all kinds of creative projects, I figured: why not try?

So I bought some parts—and that’s how this attitude indicator was born.

Alright, that’s enough backstory.

Before we get into the main content—don’t forget to like, subscribe, and hit the bell.
Okay, now let’s actually start.

What you need (hardware & software)

Here’s the full list:

A brain with ideas

A computer

A USB-C data cable

M5Dial (or any ESP32-based board)

GY-87 / MPU6050 (or any module that includes an MPU6050)

Jumper wires

A soldering iron

Two AIs

And Arduino IDE

Let me explain a few of these.

Why M5Dial?

Honestly—no deep reason.
It just looks good.

And from real-world use, it’s actually very convenient to work with.

MPU6050 (GY-87)

The important part here is the MPU6050 itself.
It includes both a gyroscope and an accelerometer.

Compared to using only an accelerometer, this combination handles both straight-line acceleration and cornering much better.
In short: more stable, more reliable data.

The two AIs: GPT and Gemini

Throughout this project, I used both GPT and Gemini.

If I imagine them as two people:

Both are excellent programmers.

But GPT feels less familiar with ESP32 development.

It’s like asking a Python expert to help you—technically correct code, but the overall structure isn’t always ideal for ESP32.

Gemini, on the other hand, seems much more comfortable with ESP32 boards.
It usually gives better overall logic and can produce a complete, working program faster.

That said, Gemini isn’t perfect.

Sometimes I ran into small issues that Gemini just couldn’t solve, no matter how many times I asked.
When that happened, I’d ask GPT—and GPT often fixed those specific problems right away.

So my personal recommendation:

Use Gemini to build the main structure.

If you get stuck on a small issue, ask GPT for help.

About “zero programming experience”

I say I’m a beginner—but realistically, I’m probably a 0.5, not a true zero.
I’ve had some programming experience before, just not with ESP32.

To be honest, even now I’m not 100% sure what language this code is written in.
And that’s completely fine.

If your goal is to learn programming from scratch, this video probably isn’t ideal.

But if your goal is to learn how to turn an idea into a working app or device, then this should still be useful.

Getting started in Arduino IDE

First, connect your hardware to the computer and open Arduino IDE.

Take a quick look around the interface.
Don’t panic just because you see code.

For anything that’s not extremely complex, AI can handle most of it.

If you’re unsure whether your idea is too complicated—ask AI first.
For example, if you want your M5Dial to time-travel, AI will probably tell you it’s impossible.
And in that case… yeah, it probably is.

At its core, Arduino IDE is mainly about writing code and uploading it.
You can’t preview the program on your computer—but upload times are short, so just wait a few seconds.

Installing board support

Before writing code, you need to install some libraries.

First:

Open Board Manager

Search for M5

Install M5Stack

Then:

Go to Tools → Board

Select M5Stack

Choose M5Dial

Now open your computer’s Device Manager.
Make sure your M5Dial is connected via USB.

You’ll see a USB serial device—note the COM port number.

Back in Arduino IDE:

Go to Tools → Port

Select that COM port

You don’t need to fully understand this.
All it does is tell Arduino IDE which device to send the code to.

Installing libraries

Next, open Library Manager.

Search for M5 and install everything related.
Then search for MPU6050 and install that as well.

These libraries save you a ton of work.
They’re basically pre-written code that you can reuse instead of starting from zero.

Even if you don’t understand what “calling a library” means—that’s okay.

A quick tip about sensors

If you want to build something else in the future using different sensors, always ask AI first:

“Does Arduino IDE have a library for this sensor?”

If a sensor has an existing library, use it.
Writing signal-reading code from scratch is much easier to mess up.

A human-written library is usually more reliable than AI making things up on the spot.

Soldering the sensor

Now we do a bit of hands-on work.

If your project doesn’t use sensors, you can skip this part.

M5Stack has dedicated data cables that plug into Port A or B—both work the same.
Each port has four wires, clearly color-coded.

The sensor pins are also labeled, so it’s basically just matching them.

For safety:
If your data cable is already connected to the M5Dial, unplug the USB-C cable before soldering.

Soldering tips

Apply some flux to the sensor board first

Then add solder—it’ll stick easily

Tin the wire with flux and a bit of solder

Place the wire on the correct pad

Touch briefly with the soldering iron

You don’t need to hold it for long.

If you’re using the GY-87 MPU6050, once everything is soldered and you plug in USB-C, the LED on the sensor should light up.

That only means power is working.
We’ll test the data connections later.

First code upload

Now open Google Gemini.

The first step is simple:
Just test the full workflow—write code → upload → see something on the M5Dial.

If you tell AI that you’re a complete beginner, it’ll guide you step by step.
That’s exactly how it guided me.

Originally, I wanted to adapt someone else’s code.
But their project used a square screen, and mine is round.
The sensor was different too.

Copy-pasting wasn’t going to work.

In the end, AI just generated everything from scratch, so I didn’t even need to reference other people’s code.

That said, when I first talked about porting existing code, AI still gave me a very solid starting approach—and that helped a lot.
