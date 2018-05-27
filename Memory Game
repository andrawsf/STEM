let light = [1]
let position = 0
function turnoff() {
    actions.setButtonLights(Buttons.Triangle, 0)
    actions.setButtonLights(Buttons.Square, 0)
    actions.setButtonLights(Buttons.Circle, 0)
    actions.setLightColor(Lights.All, Colors.Off)
}
function display() {
    for (let i = 0; i <= light.length; i++) {
        if (light.get(i) == 1) {
            actions.setButtonLights(Buttons.Circle, 255)
        }
        else if (light.get(i) == 2) {
            actions.setButtonLights(Buttons.Square, 255)
        }
        else if (light.get(i) == 3) {
            actions.setButtonLights(Buttons.Triangle, 255)
        }
        logic.wait(1.0)
        turnoff()
    }

}
function wrong() {
    actions.setLightColor(Lights.All, Colors.Red)
    logic.wait(0.5)
    turnoff()
}
function right() {
    actions.setLightColor(Lights.All, Colors.Green)
    logic.wait(0.5)
    turnoff()
    position = position + 1
}
events.whenButton(Buttons.Circle, ButtonState.Up, function () {
    if (light.get(position) == 1) {
        right()
    }
    else {
        wrong()
    }
})
events.whenButton(Buttons.Square, ButtonState.Up, function () {
    if (light.get(position) == 2) {
        right()
    }
    else {
        wrong()
    }
})
events.whenButton(Buttons.Triangle, ButtonState.Up, function () {
    if (light.get(position) == 3) {
        right()
    }
    else {
        wrong()
    }
})

// on start
while (!events.isButtonPressed(Buttons.Main)) {
    turnoff()
    position = 0
    display() // Show Pattern
    while (light.length > position) { // User Input
    }
    light.push(Math.randomRange(1, 3)) // Increase Pattern
}
