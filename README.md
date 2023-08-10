dw-button組件

---
category: Components
type: 通用
title: Button
subtitle: 按钮
---
按钮用于开始一个即时操作。

## 何时使用

标记了一个（或封装一组）操作命令，响应用户点击行为，触发相应的业务逻辑。

在 Ant Design 中，我们有四种按钮。

- 主按钮：用于主行动点，一个操作区域只能有一个主按钮。
- 默认按钮：用于没有主次之分的一组行动点。
- 虚线按钮：常用于添加操作。
- 链接按钮：用于次要或外链的行动点。

以及四种状态属性与上面配合使用。

- 危险：删除/移动/修改权限等危险操作，一般需要二次确认。
- 幽灵：用于背景色比较复杂的地方，常用在首页/产品页等展示场景。
- 禁用：行动点不可用的时候，一般需要文案解释。
- 加载中：用于异步操作等待反馈的时候，也可以避免多次提交。

```ts
import { DwButtonModule } from 'ng-zorro-antd/button';
```

## API

### [dw-button]

> 注意：dw-button 是一个 Directive，除以下表格之外还支持例如 disabled 等原生 button 的[所有属性](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/button)。

通过设置 Button 的属性来产生不同的按钮样式，推荐顺序为：`dwType` -> `dwShape` -> `dwSize` -> `dwLoading` -> `disabled`

按钮的属性说明如下：


| 属性 | 说明 | 类型 | 默认值 | 支持全局配置 |
| --- | --- | --- | --- | --- |
| `[dwGhost]` | 幽灵属性，使按钮背景透明 | `boolean` | `false` ||
| `[dwLoading]` | 设置按钮载入状态 | `boolean` | `false` ||
| `[dwShape]` | 设置按钮形状，可选值为 `circle` `round` 或者不设 | `'circle'\|'round'` | - | |
| `[dwSize]` | 设置按钮大小，可选值为 `small` `large` 或者不设 | `'large'\|'small'\|'default'` | `'default'` | ✅ |
| `[dwType]` | 设置按钮类型，可选值为 `primary` `dashed` `link` 或者不设 | `'primary'\|'dashed'\|'link'` | - ||
| `[dwBlock]` | 将按钮宽度调整为其父宽度的选项 | `boolean` | `false` ||
| `[dwDanger]` | 设置危险按钮 | boolean | `false` |  |

### dw-button-group

| 属性 | 说明 | 类型 | 默认值 | 支持全局配置 |
| --- | --- | --- | --- | --- |
| `[dwSize]` | 设置按钮大小，可选值为 `small` `large` 或者不设 | `'large'\|'small'\|'default'` | `'default'` | - |


---
order: 0
title:
  zh-CN: 按钮类型

  en-US: Type
---

## zh-CN

按钮有四种类型：主按钮、次按钮、虚线按钮和链接按钮。主按钮在同一个操作区域最多出现一次。

## en-US

There are `primary` button, `default` button, `dashed` button and `link` button in antd.

```
import { Component } from '@angular/core';

@Component({
  selector: 'dw-demo-button-basic',
  template: `
    <button dw-button dwType="primary">Primary</button>
    <button dw-button dwType="default">Default</button>
    <button dw-button dwType="dashed">Dashed</button>
    <a dw-button dwType="link">Link</a>
  `,
  styles: [
    `
      [dw-button] {
        margin-right: 8px;
        margin-bottom: 12px;
      }
    `
  ]
})
export class DwDemoButtonBasicComponent {}

```

---
order: 9
title:
  zh-CN: Block 按钮
  en-US: Block Button
---

## zh-CN

`dwBlock` 属性将使按钮适合其父宽度。

## en-US

`dwBlock` property will make the button fit to its parent width.
```
import { Component } from '@angular/core';

@Component({
  selector: 'dw-demo-button-block',
  template: `
    <button dw-button dwType="primary" dwBlock>Primary</button>
    <button dw-button dwType="default" dwBlock>Default</button>
    <button dw-button dwType="dashed" dwBlock>Dashed</button>
    <a dw-button dwType="link" dwBlock>Link</a>
  `,
  styles: [
    `
      [dw-button] {
        margin-bottom: 12px;
      }
    `
  ]
})
export class DwDemoButtonBlockComponent {}
```

---
order: 6
title:
  zh-CN: 按钮组合
  en-US: Button Group
---

## zh-CN

可以将多个 `dw-button` 放入 `dw-button-group` 的容器中。

通过设置 `dwSize` 为 `large` `small` 分别把按钮组合设为大、小尺寸。若不设置 `dwSize`，则尺寸为中。

## en-US

Buttons can be grouped by placing multiple `dw-button` components into a `dw-button-group`.

The `dwSize` can be set to `large`, `small` or left unset resulting in a default size.
```
import { Component } from '@angular/core';

@Component({
  selector: 'dw-demo-button-button-group',
  template: `
    <h4>Basic</h4>
    <dw-button-group>
      <button dw-button>Cancel</button>
      <button dw-button dwType="primary">OK</button>
    </dw-button-group>
    <dw-button-group>
      <button dw-button dwType="default" disabled>L</button>
      <button dw-button dwType="default" disabled>M</button>
      <button dw-button dwType="default" disabled>R</button>
    </dw-button-group>
    <dw-button-group>
      <button dw-button dwType="primary" disabled>L</button>
      <button dw-button dwType="default" disabled>M</button>
      <button dw-button dwType="default">M</button>
      <button dw-button dwType="dashed" disabled>R</button>
    </dw-button-group>
    <h4>With Icon</h4>
    <dw-button-group>
      <button dw-button dwType="primary"><i dw-icon dwType="left"></i> Go back</button>
      <button dw-button dwType="primary">Go forward<i dw-icon dwType="right"></i></button>
    </dw-button-group>
    <dw-button-group>
      <button dw-button dwType="primary"><i dw-icon dwType="cloud"></i></button>
      <button dw-button dwType="primary"><i dw-icon dwType="cloud-download"></i></button>
    </dw-button-group>
  `,
  styles: [
    `
      h4 {
        margin: 16px 0;
        font-size: 14px;
        line-height: 1;
        font-weight: normal;
      }

      h4:first-child {
        margin-top: 0;
      }
    
      [dw-button] {
        margin-bottom: 12px;
      }
    
      dw-button-group {
        margin-bottom: 8px;
        margin-right: 8px;
      }
    `
  ]
})
export class DwDemoButtonButtonGroupComponent {}
```

---
order: 9
title:
  zh-CN: 危险按钮
  en-US: Danger Buttons
---

## zh-CN

使用 `dwDanger` 将按钮标识为危险状态。

## en-US

You can use `dwDanger` to mark button as danger status.
```
import { Component } from '@angular/core';

@Component({
  selector: 'dw-demo-button-danger',
  template: `
    <button dw-button dwType="primary" dwDanger>Primary</button>
    <button dw-button dwType="default" dwDanger>Default</button>
    <button dw-button dwType="dashed" dwDanger>Dashed</button>
    <a dw-button dwType="link" dwDanger>Link</a>
  `,
  styles: [
    `
      [dw-button] {
        margin-right: 8px;
        margin-bottom: 12px;
      }
    `
  ]
})
export class DwDemoButtonDangerComponent {}
```


---
order: 3
title:
  zh-CN: 不可用状态
  en-US: Disabled
---

## zh-CN

添加 `disabled` 属性即可让按钮处于不可用状态，同时按钮样式也会改变。

## en-US

To mark a button as disabled, add the `disabled` property to the `Button`.
```
import { Component } from '@angular/core';

@Component({
  selector: 'dw-demo-button-disabled',
  template: `
    <button dw-button dwType="primary">Primary</button>
    <button dw-button dwType="primary" disabled>Primary(disabled)</button>
    <br />
    <button dw-button dwType="default">Default</button>
    <button dw-button dwType="default" disabled>Default(disabled)</button>
    <br />
    <button dw-button dwType="dashed">Dashed</button>
    <button dw-button dwType="dashed" disabled>Dashed(disabled)</button>
    <br />
    <a dw-button dwType="link">Link</a>
    <a dw-button dwType="link" disabled>Link(disabled)</a>
    <br />
    <a dw-button dwType="link" dwDanger>Danger Link</a>
    <a dw-button dwType="link" disabled dwDanger>Danger Link(disabled)</a>
    <br />
    <button dw-button dwType="default" dwDanger>Danger Default</button>
    <button dw-button dwType="default" disabled dwDanger>Danger Default(disabled)</button>
    <div style="padding: 8px 8px 0px; background: rgb(190, 200, 200);">
      <button dw-button dwGhost>Ghost</button>
      <button dw-button dwGhost disabled>Ghost(disabled)</button>
    </div>
  `,
  styles: [
    `
      [dw-button] {
        margin-right: 8px;
        margin-bottom: 12px;
      }
    `
  ]
})
export class DwDemoButtonDisabledComponent {}
```


---
order: 8
title:
  zh-CN: 幽灵按钮
  en-US: Ghost Button
---

## zh-CN

添加 `dwGhost` 属性后，幽灵按钮将其他按钮的内容反色，背景变为透明，常用在有色背景上。

## en-US

`dwGhost` property will make button's background transparent, it is common used in colored background.
```
import { Component } from '@angular/core';

@Component({
  selector: 'dw-demo-button-ghost',
  template: `
    <div style="background: rgb(190, 200, 200);padding: 26px 16px 16px;">
      <button dw-button dwType="primary" dwGhost>Primary</button>
      <button dw-button dwType="default" dwGhost>Default</button>
      <button dw-button dwType="dashed" dwGhost>Dashed</button>
      <a dw-button dwType="link" dwGhost>Link</a>
    </div>
  `,
  styles: [
    `
      [dw-button] {
        margin-right: 8px;
        margin-bottom: 12px;
      }
    `
  ]
})
export class DwDemoButtonGhostComponent {}
```

---
order: 1
title:
  zh-CN: 图标按钮
  en-US: Icon
---

## zh-CN

当需要在 `dw-button` 内嵌入图标时，可以直接在 `dw-button` 内嵌入对应的 `icon`。

## en-US

`dw-button` components can contain an `icon`. Just placing an `icon` within the `dw-button`
```
import { Component } from '@angular/core';

@Component({
  selector: 'dw-demo-button-icon',
  template: `
    <button dw-button dwType="primary" dwShape="circle"><i dw-icon dwType="search"></i></button>
    <button dw-button dwType="primary" dwShape="circle">A</button>
    <button dw-button dwType="primary"><i dw-icon dwType="search"></i>Search</button>
    <button dw-button dwType="default" dwShape="circle"><i dw-icon dwType="search"></i></button>
    <button dw-button dwType="default"><i dw-icon dwType="search"></i>Search</button>
    <br />
    <button dw-button dwType="default" dwShape="circle"><i dw-icon dwType="search"></i></button>
    <button dw-button dwType="default"><i dw-icon dwType="search"></i>Search</button>
    <button dw-button dwType="dashed" dwShape="circle"><i dw-icon dwType="search"></i></button>
    <button dw-button dwType="dashed"><i dw-icon dwType="search"></i>Search</button>
  `,
  styles: [
    `
      [dw-button] {
        margin-right: 8px;
        margin-bottom: 12px;
      }
    `
  ]
})
export class DwDemoButtonIconComponent {}
```


---
order: 4
title:
  zh-CN: 加载中状态
  en-US: Loading
---

## zh-CN

添加 `dwLoading` 属性即可让按钮处于加载状态，最后两个按钮演示点击后进入加载状态。

## en-US

A loading indicator can be added to a button by setting the `dwLoading` property on the `dw-button`.
```
import { Component } from '@angular/core';

@Component({
  selector: 'dw-demo-button-loading',
  template: `
    <button dw-button dwType="primary" dwLoading><i dw-icon dwType="poweroff"></i>Loading</button>
    <button dw-button dwType="primary" dwSize="small" dwLoading>Loading</button>
    <br />
    <button dw-button dwType="primary" (click)="loadOne()" [dwLoading]="isLoadingOne">Click me!</button>
    <button dw-button dwType="primary" (click)="loadTwo()" [dwLoading]="isLoadingTwo"><i dw-icon dwType="poweroff"></i>Click me!</button>
    <br />
    <button dw-button dwLoading dwShape="circle"></button>
    <button dw-button dwLoading dwType="primary" dwShape="circle"></button>
  `,
  styles: [
    `
      [dw-button] {
        margin-right: 8px;
        margin-bottom: 12px;
      }
    `
  ]
})
export class DwDemoButtonLoadingComponent {
  isLoadingOne = false;
  isLoadingTwo = false;

  loadOne(): void {
    this.isLoadingOne = true;
    setTimeout(() => {
      this.isLoadingOne = false;
    }, 5000);
  }

  loadTwo(): void {
    this.isLoadingTwo = true;
    setTimeout(() => {
      this.isLoadingTwo = false;
    }, 5000);
  }
}
```

---
order: 5
title:
  zh-CN: 多个按钮组合
  en-US: Multiple Buttons
---

## zh-CN

按钮组合使用时，推荐使用1个主操作 + n 个次操作，3个以上操作时把更多操作放到 `dw-dropdown` 中组合使用。

## en-US

If you need several buttons, we recommend that you use 1 primary button + n secondary buttons, and if there are more than three operations, you can group some of them into `dw-dropdown`.

```
import { Component } from '@angular/core';

@Component({
  selector: 'dw-demo-button-multiple',
  template: `
    <button dw-button dwType="primary">primary</button>
    <button dw-button dwType="default">secondary</button>
    <button dw-button dw-dropdown [dwDropdownMenu]="menu">Actions<i dw-icon dwType="down"></i></button>
    <dw-dropdown-menu #menu="dwDropdownMenu">
      <ul dw-menu>
        <li dw-menu-item>
          <a>1st item</a>
        </li>
        <li dw-menu-item>
          <a>2nd item</a>
        </li>
        <li dw-menu-item>
          <a>3rd item</a>
        </li>
      </ul>
    </dw-dropdown-menu>
  `,
  styles: [
    `
      [dw-button] {
        margin-right: 8px;
        margin-bottom: 12px;
      }
    `
  ]
})
export class DwDemoButtonMultipleComponent {}
```

---
order: 2
title:
  zh-CN: 按钮尺寸
  en-US: Size
---

## zh-CN

按钮有大、中、小三种尺寸。

通过设置 `dwSize` 为 `large` `small` 分别把按钮设为大、小尺寸。若不设置 `dwSize`，则尺寸为中。

## en-US

Ant Design supports a default button size as well as a large and small size.

If a large or small button is desired, set the `dwSize` property to either `large` or `small` respectively. Omit the `dwSize` property for a button with the default size.

```
import { Component } from '@angular/core';
import { DwButtonSize } from 'ng-zorro-antd/button';

@Component({
  selector: 'dw-demo-button-size',
  template: `
    <dw-radio-group [(ngModel)]="size">
      <label dw-radio-button dwValue="large">Large</label>
      <label dw-radio-button dwValue="default">Default</label>
      <label dw-radio-button dwValue="small">Small</label>
    </dw-radio-group>
    <br />
    <br />
    <button dw-button [dwSize]="size" dwType="primary">Primary</button>
    <button dw-button [dwSize]="size" dwType="default">Default</button>
    <button dw-button [dwSize]="size" dwType="dashed">Dashed</button>
    <a dw-button [dwSize]="size" dwType="link">Link</a>
    <br />
    <button dw-button dwType="primary" [dwSize]="size"><i dw-icon dwType="download"></i></button>
    <button dw-button dwType="primary" [dwSize]="size" dwShape="circle"><i dw-icon dwType="download"></i></button>
    <button dw-button dwType="primary" [dwSize]="size" dwShape="round"><i dw-icon dwType="download"></i></button>
    <button dw-button dwType="primary" [dwSize]="size" dwShape="round"><i dw-icon dwType="download"></i>Download</button>
    <button dw-button dwType="primary" [dwSize]="size"><i dw-icon dwType="download"></i>Download</button>
    <br />
    <dw-button-group [dwSize]="size">
      <button dw-button dwType="primary"><i dw-icon dwType="left"></i>Backward</button>
      <button dw-button dwType="primary">Forward<i dw-icon dwType="right"></i></button>
    </dw-button-group>
  `,
  styles: [
    `
      [dw-button] {
        margin-right: 8px;
        margin-bottom: 12px;
      }

      dw-button-group [dw-button] {
        margin-right: 0;
      }
    `
  ]
})
export class DwDemoButtonSizeComponent {
  size: DwButtonSize = 'large';
}
```
