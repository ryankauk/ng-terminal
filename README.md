# NgTerminal

[![version](https://img.shields.io/badge/ng--terminal-1.0.0-green.svg)](https://www.npmjs.com/package/ng-terminal)

NgTerminal is web terminal on Angular7 or higher. You can easily make web terminal by adding `<ng-terminal></ng-terminal>` into your component. It's written on xtermjs.

NgTerminal provides some features including [xtermjs](https://xtermjs.org/). It provides to adjust dimensions by dragging and to fix the number of rows and cols.

## Install

```
npm install ng-terminal
```

## Example

You can run a sample project in your local environment.

1) git clone https://github.com/qwefgh90/ng-terminal.git
2) npm install
3) ng serve

## Getting started

`NgTerminalModule` should be imported within **your app module.**

```typescript
import { NgTerminalModule } from 'ng-terminal';
//...
@NgModule({
    imports: [
        NgTerminalModule
    //...
```

Just add `<ng-terminal>` to your `app.component.html`.
And when you run application, you can see web terminal whose color is black.

```html
  <ng-terminal></ng-terminal>
```

Now you can print or do something on the terminal with `NgTerminal` object which has APIs for developers.
You can get a object by using `@ViewChild` in your component.

```typescript
//...
export class YourComponent implements AfterViewInit{
  @ViewChild(NgTerminalComponent) child: NgTerminal;
  
  ngAfterViewInit(){
    this.invalidate();
    this.child.keyInput.subscribe((input) => {
      this.child.write(input);
    })
  }

  //...
```

## API

#### NgTerminal

[NgTerminal](https://github.com/qwefgh90/ng-terminal/blob/changeintoxterm/projects/ng-terminal/src/lib/ng-terminal.ts) is a interface to provide public APIs you can call directly.

You can get a object by using `@ViewCHild` with a type of `NgTerminal`.

```typescript
  @ViewChild(NgTerminalComponent) child: NgTerminal;
```

#### NgTerminalComponent

[NgTerminalComponent](https://github.com/qwefgh90/ng-terminal/blob/changeintoxterm/projects/ng-terminal/src/lib/ng-terminal.component.ts) is a implementation of `NgTerminal` and a component to draw terminal where you put it.

```html
<ng-terminal></ng-terminal>
```

## Contribution

NgTerminal is devleoped with Angular CLI.
you can always write issue and contribute through PR to **master** branch.

## Reference

- ng-packagr: https://medium.com/@ngl817/building-an-angular-4-component-library-with-the-angular-cli-and-ng-packagr-53b2ade0701e
- [Telnet Keyboard Equivalents](https://www.novell.com/documentation/extend5/Docs/help/Composer/books/TelnetAppendixB.html)