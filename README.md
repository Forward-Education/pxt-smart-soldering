# pxt-fwd-solder-3b3l

Smart Solder Kit, by Forward Education.

Find us at [forwardedu.com](https://forwardedu.com/) and [learn.forwardedu.com](https://learn.forwardedu.com/). Learn more about the Smart Solder Kit on the [product page](https://forwardedu.com/products/smart-learn-to-solder-kit).

### ~ reminder

![works with micro:bit V2 only image](/static/v2/v2-only.png)

These blocks require the [micro:bit V2](/device/v2). If you use them with a V1 micro:bit you will see the 927 error code on the screen.

### ~

## Example Usage

Our learning systems are designed to simplify teaching coding and computer science for educators at all experience levels.
Our Smart Solder Kit can be used on its own or joined with other kits to access our wider library of sensors, motors, lights, and buttons.
Check out our libraries of [lessons](https://learn.forwardedu.com/lesson-library), [projects](https://learn.forwardedu.com/projects/), and [tutorials](https://learn.forwardedu.com/tutorials/).
Samples of coding with the Smart Solder Kit can be seen below. Up to 2 Smart Solder boards can be used simultaneously.
With 2 smart solder boards you will need to assign roles in the MakeCode device view to ensure the button and light assignments are correct.
With 1 smart solder board the button and light assignments are automatically assigned correctly for you in most cases.

In this code the green, yellow, and red lights are turned on and off in a sequence that simulates a traffic light. The delay variable controls how long the light stays green, yellow, or red for (a light stays on for \<delay\> seconds). The delay variable can be set to 1000, 3000, or 5000 milliseconds using the onboard buttons.

```blocks
fwdButtons.BTN2.onEvent(jacdac.ButtonEvent.Down, function () {
    delay = 3000
})
fwdButtons.BTN1.onEvent(jacdac.ButtonEvent.Down, function () {
    delay = 1000
})
fwdButtons.BTN3.onEvent(jacdac.ButtonEvent.Down, function () {
    delay = 5000
})
let delay = 0
delay = 3000
basic.forever(function () {
    fwdLights.YELLOW.setOnOff(fwdEnums.OnOff.Off)
    fwdLights.RED.setOnOff(fwdEnums.OnOff.On)
    basic.pause(delay)
    fwdLights.RED.setOnOff(fwdEnums.OnOff.Off)
    fwdLights.GREEN.setOnOff(fwdEnums.OnOff.On)
    basic.pause(delay)
    fwdLights.GREEN.setOnOff(fwdEnums.OnOff.Off)
    fwdLights.YELLOW.setOnOff(fwdEnums.OnOff.On)
    basic.pause(delay)
})
```

This code supports a survey. You are looking for red, yellow, and green items. When you find an item with one of these colors, you press the corresponding button. This will add 1 to tracking variables. You will be able to tell the last color you logged by which light is illuminated. Show the tracking variable values at any time by pressing A on the micro:bit. The results for each color will be displayed on the micro:bit for 5 seconds with the corresponding color light illuminated.

```blocks
fwdButtons.BTN3.onEvent(jacdac.ButtonEvent.Down, function () {
    fwdLights.RED.setOnOff(fwdEnums.OnOff.On)
    fwdLights.GREEN.setOnOff(fwdEnums.OnOff.Off)
    fwdLights.YELLOW.setOnOff(fwdEnums.OnOff.Off)
    redItems += 1
    basic.showNumber(redItems)
})
fwdButtons.BTN2.onEvent(jacdac.ButtonEvent.Down, function () {
    fwdLights.YELLOW.setOnOff(fwdEnums.OnOff.On)
    fwdLights.GREEN.setOnOff(fwdEnums.OnOff.Off)
    fwdLights.RED.setOnOff(fwdEnums.OnOff.Off)
    yellowItems += 1
    basic.showNumber(yellowItems)
})
input.onButtonPressed(Button.A, function () {
    fwdLights.GREEN.setOnOff(fwdEnums.OnOff.On)
    fwdLights.YELLOW.setOnOff(fwdEnums.OnOff.Off)
    fwdLights.RED.setOnOff(fwdEnums.OnOff.Off)
    basic.showNumber(greenItems)
    basic.pause(5000)
    fwdLights.GREEN.setOnOff(fwdEnums.OnOff.Off)
    fwdLights.YELLOW.setOnOff(fwdEnums.OnOff.On)
    basic.showNumber(yellowItems)
    basic.pause(5000)
    fwdLights.YELLOW.setOnOff(fwdEnums.OnOff.Off)
    fwdLights.RED.setOnOff(fwdEnums.OnOff.On)
    basic.showNumber(redItems)
    basic.pause(5000)
    fwdLights.RED.setOnOff(fwdEnums.OnOff.Off)
    basic.clearScreen()
})
fwdButtons.BTN1.onEvent(jacdac.ButtonEvent.Down, function () {
    fwdLights.GREEN.setOnOff(fwdEnums.OnOff.On)
    fwdLights.YELLOW.setOnOff(fwdEnums.OnOff.Off)
    fwdLights.RED.setOnOff(fwdEnums.OnOff.Off)
    greenItems += 1
    basic.showNumber(greenItems)
})
let yellowItems = 0
let redItems = 0
let greenItems = 0
greenItems = 0
redItems = 0
yellowItems = 0
fwdLights.GREEN.setOnOff(fwdEnums.OnOff.Off)
fwdLights.RED.setOnOff(fwdEnums.OnOff.Off)
fwdLights.YELLOW.setOnOff(fwdEnums.OnOff.Off)
```

## Supported Targets

-   for PXT/microbit

## License

MIT
