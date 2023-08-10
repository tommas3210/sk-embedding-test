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


---
category: Components
subtitle: 多选框
type: 数据录入
title: Checkbox
---

多选框。

## 何时使用

- 在一组可选项中进行多项选择时；
- 单独使用可以表示两种状态之间的切换，和 `switch` 类似。区别在于切换 `switch` 会直接触发状态改变，而 `checkbox` 一般用于状态标记，需要和提交操作配合。

```ts
import { DwCheckboxModule } from 'ng-zorro-antd/checkbox';
```

## API

### [dw-checkbox]

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| `[dwAutoFocus]` | 自动获取焦点 | `boolean` | `false` |
| `[dwDisabled]` | 设定 disable 状态 | `boolean` | `false` |
| `[ngModel]` | 指定当前是否选中，可双向绑定 | `boolean` | `false` |
| `[dwIndeterminate]` | 设置 indeterminate 状态，只负责样式控制 | `boolean` | `false` |
| `[dwValue]` | 仅与 `dw-checkbox-wrapper` 的选中回调配合使用 | `any` | - |
| `(ngModelChange)` | 选中变化时回调 | `EventEmitter<boolean>` | - |

### dw-checkbox-group

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| `[ngModel]` | 指定可选项，可双向绑定 | `Array<{ label: string; value: string; checked?: boolean; }>` | `[]` |
| `[dwDisabled]` | 设定全部 checkbox disable 状态 | `boolean` | `false` |
| `(ngModelChange)` | 选中数据变化时的回调 | `EventEmitter<Array<{ label: string; value: string; checked?: boolean; }>>` | - |


### dw-checkbox-wrapper

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| `(dwOnChange)` | 选中数据变化时的回调 | `EventEmitter<any[]>` | - |

## 方法

### [dw-checkbox]

通过ViewChild或其他方式获得 `dw-checkbox` 实例

| 名称 | 描述 |
| ---- | ----------- |
| focus() | 获取焦点 |
| blur() | 移除焦点 |

---
order: 0
title:
    zh-CN: 基本用法
    en-US: Basic
---

## zh-CN

简单的 checkbox。

## en-US

Basic usage of checkbox.

```
import { Component } from '@angular/core';

@Component({
  selector: 'dw-demo-checkbox-basic',
  template: `
    <label dw-checkbox [(ngModel)]="checked">Checkbox</label>
  `
})
export class DwDemoCheckboxBasicComponent {
  checked = true;
}
```

---
order: 4
title:
    zh-CN: 全选
    en-US: Check all
---

## zh-CN

在实现全选效果时，你可能会用到 `dwIndeterminate` 属性。

## en-US

The `dwIndeterminate` property can help you to achieve a 'check all' effect.


```
import { Component } from '@angular/core';

@Component({
  selector: 'dw-demo-checkbox-check-all',
  template: `
    <div style="border-bottom: 1px solid rgb(233, 233, 233);">
      <label dw-checkbox [(ngModel)]="allChecked" (ngModelChange)="updateAllChecked()" [dwIndeterminate]="indeterminate">
        Check all
      </label>
    </div>
    <br />
    <dw-checkbox-group [(ngModel)]="checkOptionsOne" (ngModelChange)="updateSingleChecked()"></dw-checkbox-group>
  `
})
export class DwDemoCheckboxCheckAllComponent {
  allChecked = false;
  indeterminate = true;
  checkOptionsOne = [
    { label: 'Apple', value: 'Apple', checked: true },
    { label: 'Pear', value: 'Pear', checked: false },
    { label: 'Orange', value: 'Orange', checked: false }
  ];

  updateAllChecked(): void {
    this.indeterminate = false;
    if (this.allChecked) {
      this.checkOptionsOne = this.checkOptionsOne.map(item => {
        return {
          ...item,
          checked: true
        };
      });
    } else {
      this.checkOptionsOne = this.checkOptionsOne.map(item => {
        return {
          ...item,
          checked: false
        };
      });
    }
  }

  updateSingleChecked(): void {
    if (this.checkOptionsOne.every(item => !item.checked)) {
      this.allChecked = false;
      this.indeterminate = false;
    } else if (this.checkOptionsOne.every(item => item.checked)) {
      this.allChecked = true;
      this.indeterminate = false;
    } else {
      this.indeterminate = true;
    }
  }
}
```

---
order: 2
title:
    zh-CN: 受控的 Checkbox
    en-US: Controlled Checkbox
---

## zh-CN

联动 checkbox。

## en-US

Communicated with other components.
```
import { Component } from '@angular/core';

@Component({
  selector: 'dw-demo-checkbox-controller',
  template: `
    <p style="margin-bottom: 20px;">
      <label dw-checkbox [(ngModel)]="isCheckedButton" [dwDisabled]="isDisabledButton">
        {{ isCheckedButton ? 'Checked' : 'Unchecked' }} - {{ isDisabledButton ? 'Disabled' : 'Enabled' }}
      </label>
    </p>
    <p>
      <button dw-button [dwType]="'primary'" (click)="checkButton()" [dwSize]="'small'">
        {{ !isCheckedButton ? 'Checked' : 'Unchecked' }}
      </button>
      <button dw-button [dwType]="'primary'" (click)="disableButton()" [dwSize]="'small'">
        {{ isDisabledButton ? 'Enabled' : 'Disabled' }}
      </button>
    </p>
  `,
  styles: [
    `
      button {
        margin-right: 8px;
      }
    `
  ]
})
export class DwDemoCheckboxControllerComponent {
  isCheckedButton = true;
  isDisabledButton = false;

  checkButton(): void {
    this.isCheckedButton = !this.isCheckedButton;
  }

  disableButton(): void {
    this.isDisabledButton = !this.isDisabledButton;
  }
}
```


---
order: 1
title:
    zh-CN: 不可用
    en-US: Disabled
---

## zh-CN

checkbox 不可用。

## en-US

Disabled checkbox.
```
import { Component } from '@angular/core';

@Component({
  selector: 'dw-demo-checkbox-disabled',
  template: `
    <label dw-checkbox dwDisabled [ngModel]="false"></label>
    <br />
    <label dw-checkbox dwDisabled [ngModel]="true"></label>
  `
})
export class DwDemoCheckboxDisabledComponent {}
```


---
order: 3
title:
    zh-CN: Checkbox 组
    en-US: Checkbox Group
---

## zh-CN

方便的从数组生成 Checkbox 组。

## en-US

Generate a group of checkboxes from an array.
```
import { Component } from '@angular/core';

@Component({
  selector: 'dw-demo-checkbox-group',
  template: `
    <dw-checkbox-group [(ngModel)]="checkOptionsOne" (ngModelChange)="log(checkOptionsOne)"></dw-checkbox-group>
    <br />
    <br />
    <dw-checkbox-group [(ngModel)]="checkOptionsTwo" (ngModelChange)="log(checkOptionsTwo)"></dw-checkbox-group>
    <br />
    <br />
    <dw-checkbox-group [(ngModel)]="checkOptionsThree" (ngModelChange)="log(checkOptionsThree)"></dw-checkbox-group>
  `
})
export class DwDemoCheckboxGroupComponent {
  checkOptionsOne = [
    { label: 'Apple', value: 'Apple', checked: true },
    { label: 'Pear', value: 'Pear' },
    { label: 'Orange', value: 'Orange' }
  ];
  checkOptionsTwo = [
    { label: 'Apple', value: 'Apple' },
    { label: 'Pear', value: 'Pear', checked: true },
    { label: 'Orange', value: 'Orange' }
  ];
  checkOptionsThree = [
    { label: 'Apple', value: 'Apple', disabled: true, checked: true },
    { label: 'Pear', value: 'Pear', disabled: true },
    { label: 'Orange', value: 'Orange' }
  ];

  log(value: object[]): void {
    console.log(value);
  }
}
```


---
order: 5
title:
  zh-CN: 布局
  en-US: Use with Grid
---

## zh-CN

`dw-checkbox-wrapper` 内嵌 `dw-checkbox` 并与 Grid 组件一起使用，可以实现灵活的布局。

## en-US

We can use `dw-checkbox` and Grid in `dw-checkbox-wrapper`, to implement complex layout.
```
import { Component } from '@angular/core';

@Component({
  selector: 'dw-demo-checkbox-layout',
  template: `
    <dw-checkbox-wrapper style="width: 100%;" (dwOnChange)="log($event)">
      <div dw-row>
        <div dw-col dwSpan="8"><label dw-checkbox dwValue="A" [ngModel]="true">A</label></div>
        <div dw-col dwSpan="8"><label dw-checkbox dwValue="B">B</label></div>
        <div dw-col dwSpan="8"><label dw-checkbox dwValue="C">C</label></div>
        <div dw-col dwSpan="8"><label dw-checkbox dwValue="D">D</label></div>
        <div dw-col dwSpan="8"><label dw-checkbox dwValue="E">E</label></div>
      </div>
    </dw-checkbox-wrapper>
  `
})
export class DwDemoCheckboxLayoutComponent {
  log(value: string[]): void {
    console.log(value);
  }
}
```


---
category: Components
subtitle: 输入框
type: 数据录入
title: Input
---

通过鼠标或键盘输入内容，是最基础的表单域的包装。

## 何时使用

- 需要用户输入表单域内容时。
- 提供组合型输入框，带搜索的输入框，还可以进行大小选择。

```ts
import { DwInputModule } from 'ng-zorro-antd/input';
```

## API

### [dw-input]

dw-input 可以使用所有的W3C标准下的所有 [使用方式](https://www.w3schools.com/tags/tag_input.asp) 和 Angular对 input 的全部额外功能支持。

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| `[dwSize]` | 控件大小。注：标准表单内的输入框大小限制为 `large` | `'large' \| 'small' \| 'default'` | `'default'` |
| `[dwAutosize]` | 只可以用于 `textarea`，自适应内容高度，可设置为 `boolean` 或对象：`{ minRows: 2, maxRows: 6 }` | `boolean \| { minRows: number, maxRows: number }` | `false` |

### dw-input-group

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| `[dwAddOnAfter]` | 带标签的 input，设置后置标签，可以与 `dwAddOnBefore` 配合使用 | `string \| TemplateRef<void>` | - |
| `[dwAddOnBefore]` | 带标签的 input，设置前置标签，可以与 `dwAddOnAfter` 配合使用 | `string \| TemplateRef<void>` | - |
| `[dwPrefix]` | 带有前缀图标的 input，可以与 `dwSuffix` 配合使用 | `string \| TemplateRef<void>` | - |
| `[dwSuffix]` | 带有后缀图标的 input，可以与 `dwPrefix` 配合使用 | `string \| TemplateRef<void>` | - |
| `[dwCompact]` | 是否用紧凑模式 | `boolean` | `false` |
| `[dwSearch]` | 是否用搜索框 | `boolean` | `false` |
| `[dwSize]` | `dw-input-group` 中所有的 `dw-input` 的大小 | `'large' \| 'small' \| 'default'` | `'default'` |

---
order: 2
title:
    zh-CN: 前置/后置标签
    en-US: Pre / Post tab
---

## zh-CN

用于配置一些固定组合。

## en-US

Using pre & post tabs example.
```
import { Component } from '@angular/core';

@Component({
  selector: 'dw-demo-input-addon',
  template: `
    <div>
      <dw-input-group dwAddOnBefore="Http://" dwAddOnAfter=".com">
        <input type="text" dw-input [(ngModel)]="inputValue" />
      </dw-input-group>
    </div>
    <div>
      <dw-input-group [dwAddOnBefore]="addOnBeforeTemplate" [dwAddOnAfter]="addOnAfterTemplate">
        <input type="text" dw-input [(ngModel)]="inputValue" />
      </dw-input-group>
      <ng-template #addOnBeforeTemplate>
        <dw-select [ngModel]="'Http://'">
          <dw-option dwLabel="Http://" dwValue="Http://"></dw-option>
          <dw-option dwLabel="Https://" dwValue="Https://"></dw-option>
        </dw-select>
      </ng-template>
      <ng-template #addOnAfterTemplate>
        <dw-select [ngModel]="'.com'">
          <dw-option dwLabel=".com" dwValue=".com"></dw-option>
          <dw-option dwLabel=".jp" dwValue=".jp"></dw-option>
          <dw-option dwLabel=".cn" dwValue=".cn"></dw-option>
          <dw-option dwLabel=".org" dwValue=".org"></dw-option>
        </dw-select>
      </ng-template>
    </div>
    <div>
      <dw-input-group dwAddOnAfterIcon="setting">
        <input type="text" dw-input [(ngModel)]="inputValue" />
      </dw-input-group>
    </div>
  `,
  styles: [
    `
      div {
        margin-bottom: 16px;
      }
    `
  ]
})
export class DwDemoInputAddonComponent {
  inputValue: string = 'my site';
}
```


---
order: 11
title:
    zh-CN: 带移除图标
    en-US: With clear icon
---

## zh-CN

带移除图标的输入框，点击图标删除所有内容。

## en-US

Input with clear icon.
```
import { Component } from '@angular/core';

@Component({
  selector: 'dw-demo-input-allow-clear',
  template: `
    <dw-input-group [dwSuffix]="inputClearTpl">
      <input type="text" dw-input [(ngModel)]="inputValue" placeholder="input with clear icon" />
    </dw-input-group>
    <ng-template #inputClearTpl
      ><i dw-icon class="ant-input-clear-icon" dwTheme="fill" dwType="close-circle" *ngIf="inputValue" (click)="inputValue = null"></i
    ></ng-template>
    <br />
    <br />
    <dw-input-group [dwSuffix]="textAreaClearTpl" class="ant-input-affix-wrapper-textarea-with-clear-btn">
      <textarea dw-input [(ngModel)]="textValue" placeholder="textarea with clear icon"></textarea>
    </dw-input-group>
    <ng-template #textAreaClearTpl
      ><i
        dw-icon
        class="ant-input-textarea-clear-icon"
        dwTheme="fill"
        dwType="close-circle"
        *ngIf="textValue"
        (click)="textValue = null"
      ></i
    ></ng-template>
  `
})
export class DwDemoInputAllowClearComponent {
  inputValue: string | null = null;
  textValue: string | null = null;
}
```


---
order: 6
title:
    zh-CN: 适应文本高度的文本域
    en-US: Autosizing the height to fit the content
---

## zh-CN

`dwAutosize` 属性适用于 `textarea` 节点，并且只有高度会自动变化。另外 `dwAutosize` 可以设定为一个对象，指定最小行数和最大行数。

## en-US

`dwAutosize` prop for a `textarea` type of `dw-input` makes the height to automatically adjust based on the content.
An options object can be provided to `dwAutosize` to specify the minimum and maximum number of lines the textarea will automatically adjust.
```
import { Component } from '@angular/core';

@Component({
  selector: 'dw-demo-input-autosize-textarea',
  template: `
    <div>
      <textarea dw-input placeholder="Autosize height based on content lines" dwAutosize></textarea>
      <textarea
        dw-input
        placeholder="Autosize height with minimum and maximum number of lines"
        [dwAutosize]="{ minRows: 2, maxRows: 6 }"
      ></textarea>
      <textarea dw-input placeholder="Controlled autosize" [dwAutosize]="{ minRows: 3, maxRows: 5 }"></textarea>
    </div>
  `,
  styles: [
    `
      textarea + textarea {
        margin-top: 24px;
      }
    `
  ]
})
export class DwDemoInputAutosizeTextareaComponent {}
```

```
import { Component } from '@angular/core';

@Component({
  selector: 'dw-demo-input-basic',
  template: `
    <input dw-input placeholder="Basic usage" [(ngModel)]="value" />
    <br />
    <br />
    <input dw-input placeholder="Basic usage" [(ngModel)]="value" [disabled]="true" />
  `
})
export class DwDemoInputBasicComponent {
  value?: string;
}
```

---
order: 3
title:
    zh-CN: 输入框组合
    en-US: Input Group
---

## zh-CN

输入框的组合展现。

注意：使用 `dwCompact` 模式时，不需要通过 `dw-col` 来控制宽度。

## en-US

Input.Group example

Note: You don't need `dw-col` to control the width in the `dwCompact` mode.
```
import { Component } from '@angular/core';

@Component({
  selector: 'dw-demo-input-group',
  template: `
    <dw-input-group [dwSize]="'large'">
      <div dw-row [dwGutter]="8">
        <div dw-col dwSpan="5">
          <input type="text" dw-input [ngModel]="'0571'" />
        </div>
        <div dw-col dwSpan="8">
          <input type="text" dw-input [ngModel]="'26888888'" />
        </div>
      </div>
    </dw-input-group>
    <br />
    <dw-input-group dwCompact>
      <input type="text" dw-input [ngModel]="'0571'" style="width: 20%;" />
      <input type="text" dw-input [ngModel]="'26888888'" style="width:30%;" />
    </dw-input-group>
    <br />
    <dw-input-group dwCompact>
      <dw-select [ngModel]="'Zhejiang'">
        <dw-option [dwLabel]="'Zhejiang'" [dwValue]="'Zhejiang'"></dw-option>
        <dw-option [dwLabel]="'Jiangsu'" [dwValue]="'Jiangsu'"></dw-option>
      </dw-select>
      <input type="text" dw-input [ngModel]="'Xihu District, Hangzhou'" style="width:50%;" />
    </dw-input-group>
    <br />
    <dw-input-group dwCompact>
      <dw-select [ngModel]="'Option1'">
        <dw-option [dwLabel]="'Option1'" [dwValue]="'Option1'"></dw-option>
        <dw-option [dwLabel]="'Option2'" [dwValue]="'Option2'"></dw-option>
      </dw-select>
      <input type="text" dw-input [ngModel]="'input content'" style="width:50%;" />
      <dw-input-number></dw-input-number>
    </dw-input-group>
    <br />
    <dw-input-group dwCompact>
      <input type="text" dw-input [ngModel]="'input content'" style="width:50%;" />
      <dw-date-picker></dw-date-picker>
    </dw-input-group>
    <br />
    <dw-input-group dwCompact>
      <dw-select [ngModel]="'Option1-1'">
        <dw-option [dwLabel]="'Option1-1'" [dwValue]="'Option1-1'"></dw-option>
        <dw-option [dwLabel]="'Option1-2'" [dwValue]="'Option1-2'"></dw-option>
      </dw-select>
      <dw-select [ngModel]="'Option2-1'">
        <dw-option [dwLabel]="'Option2-1'" [dwValue]="'Option2-1'"></dw-option>
        <dw-option [dwLabel]="'Option2-2'" [dwValue]="'Option2-2'"></dw-option>
      </dw-select>
    </dw-input-group>
    <br />
    <dw-input-group dwCompact>
      <dw-select [ngModel]="'Between'">
        <dw-option [dwLabel]="'Between'" [dwValue]="'Between'"></dw-option>
        <dw-option [dwLabel]="'Except'" [dwValue]="'Except'"></dw-option>
      </dw-select>
      <input type="text" dw-input placeholder="Minimum" style="width:100px; text-align: center;" />
      <input
        type="text"
        disabled
        dw-input
        placeholder="~"
        style="width: 30px; border-left: 0px; pointer-events: none; background-color: rgb(255, 255, 255);"
      />
      <input type="text" dw-input placeholder="Maximum" style="width: 100px; text-align: center; border-left: 0px;" />
    </dw-input-group>
    <br />
    <dw-input-group dwCompact>
      <dw-select [ngModel]="'Sign Up'">
        <dw-option [dwLabel]="'Sign Up'" [dwValue]="'Sign Up'"></dw-option>
        <dw-option [dwLabel]="'Sign In'" [dwValue]="'Sign In'"></dw-option>
      </dw-select>
      <input type="email" dw-input placeholder="Email" style="width: 200px;" />
    </dw-input-group>
    <br />
    <dw-input-group dwCompact>
      <dw-select [ngModel]="'Home'" style="width: 30%;">
        <dw-option [dwLabel]="'Home'" [dwValue]="'Home'"></dw-option>
        <dw-option [dwLabel]="'Company'" [dwValue]="'Company'"></dw-option>
      </dw-select>
      <dw-cascader [dwOptions]="options" style="width: 70%;"></dw-cascader>
    </dw-input-group>
  `
})
export class DwDemoInputGroupComponent {
  options = [
    {
      value: 'zhejiang',
      label: 'Zhejiang',
      children: [
        {
          value: 'hangzhou',
          label: 'Hangzhou',
          children: [
            {
              value: 'xihu',
              label: 'West Lake',
              isLeaf: true
            }
          ]
        },
        {
          value: 'ningbo',
          label: 'Ningbo',
          isLeaf: true
        }
      ]
    },
    {
      value: 'jiangsu',
      label: 'Jiangsu',
      children: [
        {
          value: 'nanjing',
          label: 'Nanjing',
          children: [
            {
              value: 'zhonghuamen',
              label: 'Zhong Hua Men',
              isLeaf: true
            }
          ]
        }
      ]
    }
  ];
}
```


---
order: 10
title:
    zh-CN: 密码框
    en-US: Password box
---

## zh-CN

密码框。

## en-US

Input type of password.
```
import { Component } from '@angular/core';

@Component({
  selector: 'dw-demo-input-password-input',
  template: `
    <dw-input-group [dwSuffix]="suffixTemplate">
      <input [type]="passwordVisible ? 'text' : 'password'" dw-input placeholder="input password" [(ngModel)]="password" />
    </dw-input-group>
    <ng-template #suffixTemplate>
      <i dw-icon [dwType]="passwordVisible ? 'eye-invisible' : 'eye'" (click)="passwordVisible = !passwordVisible"></i>
    </ng-template>
  `,
  styles: [
    `
      i {
        cursor: pointer;
      }
    `
  ]
})
export class DwDemoInputPasswordInputComponent {
  passwordVisible = false;
  password?: string;
}
```


---
order: 8
title:
    zh-CN: 前缀和后缀
    en-US: prefix and suffix
---

## zh-CN

在输入框上添加前缀或后缀图标。

## en-US

Add prefix or suffix icons inside input.
```
import { Component } from '@angular/core';

@Component({
  selector: 'dw-demo-input-presuffix',
  template: `
    <dw-input-group [dwSuffix]="suffixTemplateInfo" [dwPrefix]="prefixTemplateUser">
      <input type="text" dw-input placeholder="Enter your username" />
    </dw-input-group>
    <ng-template #prefixTemplateUser><i dw-icon dwType="user"></i></ng-template>
    <ng-template #suffixTemplateInfo><i dw-icon dw-tooltip dwTooltipTitle="Extra information" dwType="info-circle"></i></ng-template>
    <br />
    <br />
    <dw-input-group dwSuffix="RMB" dwPrefix="￥">
      <input type="text" dw-input />
    </dw-input-group>
  `
})
export class DwDemoInputPresuffixComponent {}
```


---
order: 4
title:
    zh-CN: 搜索框
    en-US: Search box
---

## zh-CN

带有搜索按钮的输入框。

## en-US

Example of creating a search box by grouping a standard input with a search button.
```
import { Component } from '@angular/core';

@Component({
  selector: 'dw-demo-input-search-input',
  template: `
    <dw-input-group [dwSuffix]="suffixIconSearch">
      <input type="text" dw-input placeholder="input search text" />
    </dw-input-group>
    <ng-template #suffixIconSearch>
      <i dw-icon dwType="search"></i>
    </ng-template>
    <br />
    <br />
    <dw-input-group dwSearch [dwAddOnAfter]="suffixIconButton">
      <input type="text" dw-input placeholder="input search text" />
    </dw-input-group>
    <ng-template #suffixIconButton>
      <button dw-button dwType="primary" dwSearch><i dw-icon dwType="search"></i></button>
    </ng-template>
    <br />
    <br />
    <dw-input-group dwSearch dwSize="large" [dwAddOnAfter]="suffixButton">
      <input type="text" dw-input placeholder="input search text" />
    </dw-input-group>
    <ng-template #suffixButton>
      <button dw-button dwType="primary" dwSize="large" dwSearch>Search</button>
    </ng-template>
  `
})
export class DwDemoInputSearchInputComponent {}
```


---
order: 1
title:
    zh-CN: 三种大小
    en-US: Three sizes of Input
---

## zh-CN

我们为 `dw-input` 输入框定义了三种尺寸（大、默认、小），高度分别为 `40px`、`32px` 和 `24px`。

注意： 在表单里面，我们只使用大尺寸的输入框。

## en-US

There are three sizes of an Input box: `large` (40px)、`default` (32px) and `small` (24px).

Note: Inside of forms, only the large size is used.
```
import { Component } from '@angular/core';

@Component({
  selector: 'dw-demo-input-size',
  template: `
    <div class="example-input">
      <input dw-input placeholder="large size" dwSize="large" />
      <input dw-input placeholder="default size" dwSize="default" />
      <input dw-input placeholder="small size" dwSize="small" />
    </div>
  `,
  styles: [
    `
      .example-input .ant-input {
        width: 200px;
        margin: 0 8px 8px 0;
      }
    `
  ]
})
export class DwDemoInputSizeComponent {}
```


---
order: 5
title:
    zh-CN: 文本域
    en-US: TextArea
---

## zh-CN

用于多行输入。

## en-US

For multi-line input.
```
import { Component } from '@angular/core';

@Component({
  selector: 'dw-demo-input-textarea',
  template: `
    <textarea rows="4" dw-input [(ngModel)]="inputValue"></textarea>
  `
})
export class DwDemoInputTextareaComponent {
  inputValue?: string;
}
```


---
order: 7
title:
    zh-CN: 输入时格式化展示
    en-US: Format Tooltip Input
---

## zh-CN

结合 [Tooltip](/components/tooltip/zh) 组件，实现一个数值输入框，方便内容超长时的全量展现。

## en-US

You can use the Input in conjunction with [Tooltip](/components/tooltip/en) component to create a Numeric Input, which can provide a good experience for extra-long content display.
```
import { Component, ElementRef, ViewChild, ViewEncapsulation } from '@angular/core';

@Component({
  selector: 'dw-demo-input-tooltip',
  encapsulation: ViewEncapsulation.None,
  template: `
    <input
      #inputElement
      style="width: 120px"
      dw-input
      dw-tooltip
      dwTooltipTrigger="focus"
      dwTooltipPlacement="topLeft"
      dwOverlayClassName="numeric-input"
      [ngModel]="value"
      [dwTooltipTitle]="title"
      placeholder="Input a number"
      (ngModelChange)="onChange($event)"
      (blur)="onBlur()"
    />
  `,
  styles: [
    `
      .numeric-input .ant-tooltip-inner {
        min-width: 32px;
        min-height: 37px;
      }

      .numeric-input .numeric-input-title {
        font-size: 14px;
      }
    `
  ]
})
export class DwDemoInputTooltipComponent {
  value = '';
  title = 'Input a number';

  @ViewChild('inputElement', { static: false }) inputElement?: ElementRef;

  onChange(value: string): void {
    this.updateValue(value);
  }

  // '.' at the end or only '-' in the input box.
  onBlur(): void {
    if (this.value.charAt(this.value.length - 1) === '.' || this.value === '-') {
      this.updateValue(this.value.slice(0, -1));
    }
  }

  updateValue(value: string): void {
    const reg = /^-?(0|[1-9][0-9]*)(\.[0-9]*)?$/;
    if ((!isNaN(+value) && reg.test(value)) || value === '' || value === '-') {
      this.value = value;
    }
    this.inputElement!.nativeElement.value = this.value;
    this.updateTitle();
  }

  updateTitle(): void {
    this.title = (this.value !== '-' ? this.formatNumber(this.value) : '-') || 'Input a number';
  }

  formatNumber(value: string): string {
    const stringValue = `${value}`;
    const list = stringValue.split('.');
    const prefix = list[0].charAt(0) === '-' ? '-' : '';
    let num = prefix ? list[0].slice(1) : list[0];
    let result = '';
    while (num.length > 3) {
      result = `,${num.slice(-3)}${result}`;
      num = num.slice(0, num.length - 3);
    }
    if (num) {
      result = num + result;
    }
    return `${prefix}${result}${list[1] ? `.${list[1]}` : ''}`;
  }
}
```


---
category: Components
subtitle: 数字输入框
type: 数据录入
title: InputNumber
---

通过鼠标或键盘，输入范围内的数值。

## 何时使用

当需要获取标准数值时。

```ts
import { DwInputNumberModule } from 'ng-zorro-antd/input-number';
```

## API

### dw-input-number

| 成员 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| `[ngModel]` | 当前值，可双向绑定 | `number \| string`  \|  `string` | - |
| `[dwAutoFocus]` | 自动获取焦点 | `boolean` | `false` |
| `[dwDisabled]` | 禁用 | `boolean` | `false` |
| `[dwMax]` | 最大值 | `number` | `Infinity` |
| `[dwMin]` | 最小值 | `number` | `-Infinity` |
| `[dwFormatter]` | 指定输入框展示值的格式 | `(value: number \| string) => string \| number` | - |
| `[dwParser]` | 指定从 dwFormatter 里转换回数字的方式，和 dwFormatter 搭配使用 | `(value: string) => string \| number` | `(value: string) => value.trim().replace(/。/g, '.').replace(/[^\w\.-]+/g, '')` |
| `[dwPrecision]` | 数值精度 | `number` | - |
| `[dwPrecisionMode]` | 数值精度的取值方式 | `'cut' \| 'toFixed' \| ((value: number \| string, precision?: number) => number)` | `'toFixed'` |
| `[dwSize]` | 输入框大小 | `'large' \| 'small' \| 'default'` | `'default'` |
| `[dwStep]` | 每次改变步数，可以为小数 | `number \| string` | `1` |
| `[dwInputMode]` | 提供了用户在编辑元素或其内容时可能输入的数据类型的提示，详见[MDN](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Global_attributes/inputmode) | `string` | `decimal` |
| `[dwPlaceHolder]` | 选择框默认文字 | `string` | - |
| `[dwId]` | 组件内部 input 的 id 值 | `string` | - |
| `(ngModelChange)` | 数值改变时回调 | `EventEmitter<number>` | - |
| `(dwFocus)` | focus时回调 | `EventEmitter<void>` | - |
| `(dwBlur)` | blur时回调 | `EventEmitter<void>` | - |

#### 方法

通过 `ViewChild` 等方法获得实例后调用

| 名称 | 描述 |
| ---- | ----------- |
| focus() | 获取焦点 |
| blur() | 移除焦点 |
---
order: 0
title:
    zh-CN: 基本
    en-US: Basic
---

## zh-CN

数字输入框。

## en-US

Numeric-only input box.

```
import { Component } from '@angular/core';

@Component({
  selector: 'dw-demo-input-number-basic',
  template: `
    <dw-input-number [(ngModel)]="demoValue" [dwMin]="1" [dwMax]="10" [dwStep]="1"></dw-input-number>
  `
})
export class DwDemoInputNumberBasicComponent {
  demoValue = 3;
}
```


---
order: 3
title:
    zh-CN: 小数
    en-US: Decimals
---

## zh-CN

和原生的数字输入框一样，value 的精度由 `dwStep` 的小数位数决定。

## en-US

A numeric-only input box whose values can be increased or decreased using a decimal step. The number of decimals (also known as precision) is determined by the `dwStep` prop.
```
import { Component } from '@angular/core';

@Component({
  selector: 'dw-demo-input-number-digit',
  template: `
    <dw-input-number [(ngModel)]="demoValue" [dwMin]="1" [dwMax]="10" [dwStep]="0.1" [dwPlaceHolder]="'Digital'"></dw-input-number>
  `
})
export class DwDemoInputNumberDigitComponent {
  demoValue: number = 0;
}
```


---
order: 2
title:
    zh-CN: 不可用
    en-US: Disabled
---

## zh-CN

点击按钮切换可用状态。

## en-US

Click the button to toggle between available and disabled states.
```
import { Component } from '@angular/core';

@Component({
  selector: 'dw-demo-input-number-disabled',
  template: `
    <dw-input-number [(ngModel)]="demoValue" [dwMin]="1" [dwMax]="10" [dwStep]="1" [dwDisabled]="isDisabled"></dw-input-number>
    <div style="margin-top:20px;">
      <button dw-button [dwType]="'primary'" (click)="toggleDisabled()">
        <span>Toggle Disabled</span>
      </button>
    </div>
  `
})
export class DwDemoInputNumberDisabledComponent {
  demoValue = 3;
  isDisabled = false;

  toggleDisabled(): void {
    this.isDisabled = !this.isDisabled;
  }
}
```


---
order: 4
title:
    zh-CN: 格式化展示
    en-US: Formatter
---

## zh-CN

通过 `dwFormatter` 格式化数字，以展示具有具体含义的数据，往往需要配合 `dwParser` 一起使用。

## en-US

Display value within it's situation with `dwFormatter`, and we usually use `dwParser` at the same time.
```
import { Component } from '@angular/core';

@Component({
  selector: 'dw-demo-input-number-formatter',
  template: `
    <dw-input-number
      [(ngModel)]="demoValue"
      [dwMin]="1"
      [dwMax]="100"
      [dwStep]="1"
      [dwFormatter]="formatterDollar"
      [dwParser]="parserDollar"
    ></dw-input-number>
    <dw-input-number
      [(ngModel)]="demoValue"
      [dwMin]="1"
      [dwMax]="100"
      [dwStep]="1"
      [dwFormatter]="formatterPercent"
      [dwParser]="parserPercent"
    ></dw-input-number>
  `,
  styles: [
    `
      dw-input-number {
        margin-right: 8px;
      }
    `
  ]
})
export class DwDemoInputNumberFormatterComponent {
  demoValue = 100;
  formatterPercent = (value: number) => `${value} %`;
  parserPercent = (value: string) => value.replace(' %', '');
  formatterDollar = (value: number) => `$ ${value}`;
  parserDollar = (value: string) => value.replace('$ ', '');
}
```


---
order: 5
title:
    zh-CN: 精度
    en-US: Precision
---

## zh-CN

指定 value 的精度

## en-US

Set precision of the value
```
import { Component } from '@angular/core';

@Component({
  selector: 'dw-demo-input-number-precision',
  template: `
    <dw-input-number [(ngModel)]="toFixedValue" [dwPrecision]="precision" dwPlaceHolder="toFixed"></dw-input-number>
    <dw-input-number [(ngModel)]="cutValue" [dwPrecision]="precision" dwPrecisionMode="cut" dwPlaceHolder="cut off"></dw-input-number>
    <dw-input-number
      [(ngModel)]="customFnValue"
      [dwPrecision]="precision"
      [dwPrecisionMode]="customPrecisionFn"
      dwPlaceHolder="cut off"
    ></dw-input-number>
  `,
  styles: [
    `
      dw-input-number {
        margin-right: 8px;
      }
    `
  ]
})
export class DwDemoInputNumberPrecisionComponent {
  toFixedValue = 2;
  cutValue = 2;
  customFnValue = 2;
  precision = 2;
  customPrecisionFn(value: string | number, precision?: number): number {
    return +Number(value).toFixed(precision! + 1);
  }
}
```


---
order: 1
title:
    zh-CN: 三种大小
    en-US: Sizes
---

## zh-CN

三种大小的数字输入框，当 `dwSize` 分别为 `large` 和 `small` 时，输入框高度为 `40px` 和 `24px` ，默认高度为 `32px`。

## en-US

There are three sizes available to a numeric input box. By default, the `dwSize` is `32px`. The two additional sizes are `large` and `small` which means `40px` and `24px`, respectively.
```
import { Component } from '@angular/core';

@Component({
  selector: 'dw-demo-input-number-size',
  template: `
    <dw-input-number [(ngModel)]="demoValue" [dwSize]="'large'" [dwMin]="1" [dwMax]="10" [dwStep]="1"></dw-input-number>
    <dw-input-number [(ngModel)]="demoValue" [dwMin]="1" [dwMax]="10" [dwStep]="1"></dw-input-number>
    <dw-input-number [(ngModel)]="demoValue" [dwSize]="'small'" [dwMin]="1" [dwMax]="10" [dwStep]="1"></dw-input-number>
  `,
  styles: [
    `
      dw-input-number {
        margin-right: 8px;
      }
    `
  ]
})
export class DwDemoInputNumberSizeComponent {
  demoValue = 3;
}
```


---
category: Components
subtitle: 选择器
type: 数据录入
title: Select
---

下拉选择器。

## 何时使用

- 弹出一个下拉菜单给用户选择操作，用于代替原生的选择器，或者需要一个更优雅的多选器时。
- 当选项少时（少于 5 项），建议直接将选项平铺，使用 [Radio](/components/radio/zh) 是更好的选择。

```ts
import { DwSelectModule } from 'ng-zorro-antd/select';
```

## API

```html
<dw-select>
  <dw-option dwValue="lucy" dwLabel="Lucy"></dw-option>
</dw-select>
```

### dw-select

| 参数 | 说明 | 类型 | 默认值 | 全局配置 |
| --- | --- | --- | --- | --- |
| `[ngModel]` | 当前选中的 dw-option 的 dwValue 值，可双向绑定，当 `dwMode` 为 `multiple` 或 `tags` 时，ngModel 为数组 | `any \| any[]` | - |
| `[compareWith]` | 与 [SelectControlValueAccessor](https://angular.io/api/forms/SelectControlValueAccessor#caveat-option-selection) 相同 | `(o1: any, o2: any) => boolean` | `(o1: any, o2: any) => o1===o2` |
| `[dwAutoClearSearchValue]` | 是否在选中项后清空搜索框，只在 `mode` 为 `multiple` 或 `tags` 时有效。 | boolean | `true` |
| `[dwAllowClear]` | 支持清除 | `boolean` | `false` |
| `[dwBorderless]` | 是否无边框 | `boolean` | `false` | ✅ |
| `[dwOpen]` | 下拉菜单是否打开，可双向绑定 | `boolean` | `false` |
| `[dwAutoFocus]` | 默认获取焦点 | `boolean` | `false` |
| `[dwDisabled]` | 是否禁用 | `boolean` | `false` |
| `[dwDropdownClassName]` | 下拉菜单的 className 属性 | `string` | - |
| `[dwDropdownMatchSelectWidth]` | 下拉菜单和选择器同宽 | `boolean` | `true` |
| `[dwDropdownStyle]` | 下拉菜单的 style 属性 | `object` | - |
| `[dwCustomTemplate]` | 自定义选择框的Template内容 | `TemplateRef<{ $implicit: DwOptionComponent }>` | - |
| `[dwServerSearch]` | 是否使用服务端搜索，当为 true 时，将不再在前端对 dw-option 进行过滤 | `boolean` | `false` |
| `[dwFilterOption]` | 是否根据输入项进行筛选。当其为一个函数时，会接收 `inputValue` `option` 两个参数，当 `option` 符合筛选条件时，应返回 `true`，反之则返回 `false`。 | `(input?: string, option?: DwOptionComponent) => boolean;` | - |
| `[dwMaxMultipleCount]` | 最多选中多少个标签| `number` | `Infinity` |
| `[dwMode]` | 设置 dw-select 的模式 | `'multiple' \| 'tags' \| 'default'` | `'default'` |
| `[dwNotFoundContent]` | 当下拉列表为空时显示的内容 | `string \| TemplateRef<void>` | - |
| `[dwPlaceHolder]` | 选择框默认文字 | `string` | - |
| `[dwShowArrow]` | 是否显示下拉小箭头 | `boolean` | `true` |
| `[dwShowSearch]` | 使单选模式可搜索 | `boolean` | `false` |
| `[dwSize]` | 选择框大小 | `'large' \| 'small' \| 'default'` | `'default'` |
| `[dwSuffixIcon]` | 自定义的选择框后缀图标 | `TemplateRef<any> \| string` | - | ✅ |
| `[dwRemoveIcon]` | 自定义的多选框清除图标 | `TemplateRef<any>` | - |
| `[dwClearIcon]` | 自定义的多选框清空图标 | `TemplateRef<any>` | - |
| `[dwMenuItemSelectedIcon]` | 自定义当前选中的条目图标 | `TemplateRef<any>` | - |
| `[dwTokenSeparators]` | 在 tags 和 multiple 模式下自动分词的分隔符 | `string[]` | `[]` |
| `[dwLoading]` | 加载中状态 | `boolean` | `false` |
| `[dwMaxTagCount]` | 最多显示多少个 tag | `number` | - |
| `[dwMaxTagPlaceholder]` | 隐藏 tag 时显示的内容 | `TemplateRef<{ $implicit: any[] }>` | - |
| `[dwOptions]` | option 列表，可以取代 dw-option，用法参见例子 | `Array<{ label: string \| TemplateRef<any>; value: any; disabled?: boolean; hide?: boolean; groupLabel?: string \| TemplateRef<any>;}>` | - |
| `[dwOptionHeightPx]` | 下拉菜单中每个 Option 的高度 | `number` | `32` |
| `[dwOptionOverflowSize]` | 下拉菜单中最多展示的 Option 个数，超出部分滚动 | `number` | `8` |
| `(ngModelChange)` | 选中的 dw-option 发生变化时，调用此函数 | `EventEmitter<any[]>` | - |
| `(dwOpenChange)` | 下拉菜单打开状态变化回调 | `EventEmitter<boolean>` | - |
| `(dwScrollToBottom)` | 下拉列表滚动到底部的回调 | `EventEmitter<any>` | - |
| `(dwOnSearch)` | 文本框值变化时回调 | `EventEmitter<string>` | - |
| `(dwFocus)` | focus时回调 | `EventEmitter<any>` | - |
| `(dwBlur)` | blur时回调 | `EventEmitter<any>` | - |

### dw-option

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| `[dwDisabled]` | 是否禁用 | `boolean` | `false` |
| `[dwLabel]` | 选中该 dw-option 后，dw-select 中显示的文字 | `string` | - |
| `[dwValue]` | dw-select 中 ngModel 的值 | `any` | - |
| `[dwHide]` | 是否在选项列表中隐藏改选项 | `boolean` | `false` |
| `[dwCustomContent]` | 是否自定义在下拉菜单中的Template内容，当为 true 时，dw-option 包裹的内容将直接渲染在下拉菜单中 | `boolean` | `false` |

### dw-option-group

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| `[dwLabel]` | 组名 | `string \| TemplateRef<void>` | - |


## 方法

### dw-select

| 名称 | 说明 |
| --- | --- |
| blur() | 取消焦点 |
| focus() | 获取焦点 |

---
order: 0
title:
  zh-CN: 基本使用
  en-US: Basic Usage
---

## zh-CN

基本使用。

## en-US

Basic Usage.
```
import { Component } from '@angular/core';

@Component({
  selector: 'dw-demo-select-basic',
  template: `
    <dw-select ngModel="lucy">
      <dw-option dwValue="jack" dwLabel="Jack"></dw-option>
      <dw-option dwValue="lucy" dwLabel="Lucy"></dw-option>
      <dw-option dwValue="disabled" dwLabel="Disabled" dwDisabled></dw-option>
    </dw-select>
    <dw-select ngModel="lucy" dwDisabled>
      <dw-option dwValue="lucy" dwLabel="Lucy"></dw-option>
    </dw-select>
    <dw-select ngModel="lucy" dwLoading>
      <dw-option dwValue="lucy" dwLabel="Lucy"></dw-option>
    </dw-select>
    <dw-select ngModel="lucy" dwAllowClear dwPlaceHolder="Choose">
      <dw-option dwValue="lucy" dwLabel="Lucy"></dw-option>
    </dw-select>
  `,
  styles: [
    `
      dw-select {
        margin: 0 8px 10px 0;
        width: 120px;
      }
    `
  ]
})
export class DwDemoSelectBasicComponent {}
```

---
order: 12
title:
  zh-CN: 自动分词
  en-US: Automatic tokenization
---

## zh-CN

试下复制 `露西,杰克` 到输入框里。只在 tags 和 multiple 模式下可用。

## en-US

Try to copy `Lucy,Jack` to the input. Only available in tags and multiple mode.
```
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'dw-demo-select-automatic-tokenization',
  template: `
    <dw-select [(ngModel)]="listOfTagOptions" dwMode="tags" [dwTokenSeparators]="[',']" dwPlaceHolder="automatic tokenization">
      <dw-option *ngFor="let option of listOfOption" [dwLabel]="option.label" [dwValue]="option.value"></dw-option>
    </dw-select>
  `,
  styles: [
    `
      dw-select {
        width: 100%;
      }
    `
  ]
})
export class DwDemoSelectAutomaticTokenizationComponent implements OnInit {
  listOfOption: Array<{ label: string; value: string }> = [];
  listOfTagOptions = [];

  ngOnInit(): void {
    const children: Array<{ label: string; value: string }> = [];
    for (let i = 10; i < 36; i++) {
      children.push({ label: i.toString(36) + i, value: i.toString(36) + i });
    }
    this.listOfOption = children;
  }
}
```


---
order: 20
title:
  zh-CN: 大量数据
  en-US: Large amounts of data
---

## zh-CN

组件使用了虚拟滚动技术，可以同时处理大量数据。

## en-US

With the help of virtual scroll, select component can deal with Large amounts of data.
```
import { ChangeDetectionStrategy, Component, OnInit } from '@angular/core';

@Component({
  selector: 'dw-demo-select-big-data',
  changeDetection: ChangeDetectionStrategy.OnPush,
  template: `
    <dw-select dwMode="multiple" dwPlaceHolder="Please select" [dwOptions]="listOfOption" [(ngModel)]="listOfSelectedValue"> </dw-select>
  `,
  styles: [
    `
      dw-select {
        width: 100%;
      }
    `
  ]
})
export class DwDemoSelectBigDataComponent implements OnInit {
  listOfOption: Array<{ value: string; label: string }> = [];
  listOfSelectedValue = ['a10', 'c12'];

  ngOnInit(): void {
    const children: string[] = [];
    for (let i = 10; i < 10000; i++) {
      children.push(`${i.toString(36)}${i}`);
    }
    this.listOfOption = children.map(item => {
      return {
        value: item,
        label: item
      };
    });
  }
}
```


---
order: 21
title:
  zh-CN: 无边框
  en-US: Bordered-less
---

## zh-CN

无边框样式。

## en-US

Bordered-less style component.
```
import { Component } from '@angular/core';

@Component({
  selector: 'dw-demo-select-border-less',
  template: `
    <dw-select ngModel="lucy" dwBorderless>
      <dw-option dwValue="jack" dwLabel="Jack"></dw-option>
      <dw-option dwValue="lucy" dwLabel="Lucy"></dw-option>
      <dw-option dwValue="disabled" dwLabel="Disabled" dwDisabled></dw-option>
    </dw-select>
    <dw-select ngModel="lucy" dwDisabled dwBorderless>
      <dw-option dwValue="lucy" dwLabel="Lucy"></dw-option>
    </dw-select>
  `,
  styles: [
    `
      dw-select {
        margin: 0 8px 10px 0;
        width: 120px;
      }
    `
  ]
})
export class DwDemoSelectBorderLessComponent {}
```


---
order: 7
title:
  zh-CN: 联动
  en-US: coordinate
---

## zh-CN

省市联动是典型的例子。

推荐使用 [Cascader](/components/cascader/zh) 组件。

## en-US

Coordinating the selection of provinces and cities is a common use case and demonstrates how selection can be coordinated.

Using the [Cascader](/components/cascader/en) component is strongly recommended instead as it is more flexible and capable.
```
import { Component } from '@angular/core';

@Component({
  selector: 'dw-demo-select-coordinate',
  template: `
    <div>
      <dw-select [(ngModel)]="selectedProvince" (ngModelChange)="provinceChange($event)">
        <dw-option *ngFor="let p of provinceData" [dwValue]="p" [dwLabel]="p"></dw-option>
      </dw-select>
      <dw-select [(ngModel)]="selectedCity">
        <dw-option *ngFor="let c of cityData[selectedProvince]" [dwValue]="c" [dwLabel]="c"></dw-option>
      </dw-select>
    </div>
  `,
  styles: [
    `
      dw-select {
        margin-right: 8px;
        width: 120px;
      }
    `
  ]
})
export class DwDemoSelectCoordinateComponent {
  selectedProvince = 'Zhejiang';
  selectedCity = 'Hangzhou';
  provinceData = ['Zhejiang', 'Jiangsu'];
  cityData: { [place: string]: string[] } = {
    Zhejiang: ['Hangzhou', 'Ningbo', 'Wenzhou'],
    Jiangsu: ['Nanjing', 'Suzhou', 'Zhenjiang']
  };

  provinceChange(value: string): void {
    this.selectedCity = this.cityData[value][0];
  }
}
```


---
order: 16
title:
  zh-CN: 自定义下拉菜单内容
  en-US: Custom Option Template
---

## zh-CN

通过 `dwCustomContent` 自定义下拉菜单选项显示的内容。

## en-US

Custom the content of dw-option via `dwCustomContent`.
```
import { Component } from '@angular/core';

@Component({
  selector: 'dw-demo-select-custom-content',
  template: `
    <dw-select dwShowSearch dwAllowClear dwPlaceHolder="Select OS" [(ngModel)]="selectedOS">
      <dw-option dwCustomContent dwLabel="Windows" dwValue="windows"><i dw-icon dwType="windows"></i> Windows</dw-option>
      <dw-option dwCustomContent dwLabel="Mac" dwValue="mac"><i dw-icon dwType="apple"></i> Mac</dw-option>
      <dw-option dwCustomContent dwLabel="Android" dwValue="android"><i dw-icon dwType="android"></i> Android </dw-option>
    </dw-select>
  `,
  styles: [
    `
      dw-select {
        width: 200px;
      }
    `
  ]
})
export class DwDemoSelectCustomContentComponent {
  selectedOS = null;
}
```


---
order: 14
title:
  zh-CN: 扩展菜单
  en-US: Custom dropdown
---

## zh-CN

使用 `dwDropdownRender` 对下拉菜单进行自由扩展。

## en-US

Customize the dropdown menu via `dwDropdownRender`.
```
import { Component } from '@angular/core';

@Component({
  selector: 'dw-demo-select-custom-dropdown-menu',
  template: `
    <dw-select dwShowSearch dwAllowClear [dwDropdownRender]="renderTemplate" dwPlaceHolder="custom dropdown render">
      <dw-option *ngFor="let item of listOfItem" [dwLabel]="item" [dwValue]="item"></dw-option>
    </dw-select>
    <ng-template #renderTemplate>
      <dw-divider></dw-divider>
      <div class="container">
        <input type="text" dw-input #inputElement />
        <a class="add-item" (click)="addItem(inputElement)"><i dw-icon dwType="plus"></i> Add item</a>
      </div>
    </ng-template>
  `,
  styles: [
    `
      dw-select {
        width: 240px;
      }
      dw-divider {
        margin: 4px 0;
      }
      .container {
        display: flex;
        flex-wrap: nowrap;
        padding: 8px;
      }
      input {
      }
      .add-item {
        flex: 0 0 auto;
        padding: 8px;
        display: block;
      }
    `
  ]
})
export class DwDemoSelectCustomDropdownMenuComponent {
  listOfItem = ['jack', 'lucy'];
  index = 0;
  addItem(input: HTMLInputElement): void {
    const value = input.value;
    if (this.listOfItem.indexOf(value) === -1) {
      this.listOfItem = [...this.listOfItem, input.value || `New item ${this.index++}`];
    }
  }
}
```


---
order: 22
title:
  zh-CN: 自定义选择标签
  en-US: Custom Top Render
---

## zh-CN

通过 `dwCustomTemplate` 自定义 dw-select 显示的内容。

## en-US

Custom the content of dw-select via `dwCustomTemplate`.
```
import { Component } from '@angular/core';

@Component({
  selector: 'dw-demo-select-custom-template',
  template: `
    <dw-select dwAllowClear dwPlaceHolder="Select OS" [dwCustomTemplate]="defaultTemplate">
      <dw-option dwLabel="Windows" dwValue="windows"></dw-option>
      <dw-option dwLabel="Apple" dwValue="apple"></dw-option>
      <dw-option dwLabel="Android" dwValue="android"></dw-option>
    </dw-select>
    <ng-template #defaultTemplate let-selected> <i dw-icon [dwType]="selected.dwValue"></i> {{ selected.dwLabel }} </ng-template>
    <br />
    <br />
    <dw-select dwAllowClear dwPlaceHolder="Select OS" dwMode="multiple" [dwCustomTemplate]="multipleTemplate">
      <dw-option dwLabel="Windows" dwValue="windows"></dw-option>
      <dw-option dwLabel="Apple" dwValue="apple"></dw-option>
      <dw-option dwLabel="Android" dwValue="android"></dw-option>
    </dw-select>
    <ng-template #multipleTemplate let-selected>
      <div class="ant-select-selection-item-content"><i dw-icon [dwType]="selected.dwValue"></i> {{ selected.dwLabel }}</div>
    </ng-template>
  `,
  styles: [
    `
      dw-select {
        width: 100%;
      }
    `
  ]
})
export class DwDemoSelectCustomTemplateComponent {}
```


---
order: 19
title:
  zh-CN: 默认数据
  en-US: Default Value
---

## zh-CN

当需要显示默认值，同时默认值又不在选项列表中时，可以使用 `dwHide` 在 `dw-option` 中将默认选项隐藏

## en-US

Display a default value that not in the option list with `dwHide` in `dw-option`
```
import { Component } from '@angular/core';

@Component({
  selector: 'dw-demo-select-default-value',
  template: `
    <dw-select dwMode="multiple" dwPlaceHolder="Inserted are removed" [(ngModel)]="listOfSelectedValue">
      <dw-option *ngFor="let option of listOfOption" [dwLabel]="option" [dwValue]="option"></dw-option>
      <dw-option *ngFor="let option of defaultOption" [dwLabel]="option" [dwValue]="option" dwHide></dw-option>
    </dw-select>
    <br />
    <br />
    <dw-select [(ngModel)]="selectedValue">
      <dw-option *ngFor="let option of listOfOption" [dwLabel]="option" [dwValue]="option"></dw-option>
      <dw-option dwLabel="Default Value" dwValue="Default" dwHide></dw-option>
    </dw-select>
  `,
  styles: [
    `
      dw-select {
        width: 100%;
      }
    `
  ]
})
export class DwDemoSelectDefaultValueComponent {
  listOfOption = ['Option 01', 'Option 02'];
  listOfSelectedValue = ['Default 01', 'Default 02'];
  defaultOption = [...this.listOfSelectedValue];

  selectedValue = 'Default';
}
```


---
order: 15
title:
  zh-CN: 隐藏已选择选项
  en-US: Hide Already Selected
---

## zh-CN

通过 `dwHide` 隐藏下拉列表中已选择的选项。

## en-US

Hide already selected options in the dropdown via `dwHide`.
```
import { Component } from '@angular/core';

@Component({
  selector: 'dw-demo-select-hide-selected',
  template: `
    <dw-select dwMode="multiple" dwPlaceHolder="Inserted are removed" [(ngModel)]="listOfSelectedValue">
      <dw-option *ngFor="let option of listOfOption" [dwLabel]="option" [dwValue]="option" [dwHide]="!isNotSelected(option)"></dw-option>
    </dw-select>
  `,
  styles: [
    `
      dw-select {
        width: 100%;
      }
    `
  ]
})
export class DwDemoSelectHideSelectedComponent {
  listOfOption = ['Apples', 'Nails', 'Bananas', 'Helicopters'];
  listOfSelectedValue: string[] = [];

  isNotSelected(value: string): boolean {
    return this.listOfSelectedValue.indexOf(value) === -1;
  }
}
```


---
order: 10
title:
  zh-CN: 获得选项的对象
  en-US: Get option object of selected item
---

## zh-CN

`ngModel` 取到的值为选中 `dw-option` 的 `dwValue` 值，当 `dwValue` 传入为一个对象时，`ngModel` 获取的值也是一个对象，`compareWith` 的用法参见 [这里](https://angular.io/api/forms/SelectControlValueAccessor#caveat-option-selection).

## en-US

The value of `ngModel` comes from the `dwValue` of `dw-option`, when the `dwValue` of `dw-option`  is an object, the `ngModel` will be an object too, the usage of `compareWith` is the same as [SelectControlValueAccessor](https://angular.io/api/forms/SelectControlValueAccessor#caveat-option-selection).
```
import { Component } from '@angular/core';

@Component({
  selector: 'dw-demo-select-label-in-value',
  template: `
    <p>The selected option's age is {{ selectedValue?.age }}</p>
    <br />
    <dw-select [(ngModel)]="selectedValue" [compareWith]="compareFn" (ngModelChange)="log($event)" dwAllowClear dwPlaceHolder="Choose">
      <dw-option *ngFor="let option of optionList" [dwValue]="option" [dwLabel]="option.label"></dw-option>
    </dw-select>
  `,
  styles: [
    `
      dw-select {
        width: 120px;
      }
    `
  ]
})
export class DwDemoSelectLabelInValueComponent {
  optionList = [
    { label: 'Lucy', value: 'lucy', age: 20 },
    { label: 'Jack', value: 'jack', age: 22 }
  ];
  selectedValue = { label: 'Jack', value: 'jack', age: 22 };
  // tslint:disable-next-line:no-any
  compareFn = (o1: any, o2: any) => (o1 && o2 ? o1.value === o2.value : o1 === o2);

  log(value: { label: string; value: string; age: number }): void {
    console.log(value);
  }
}
```


---
order: 2
title:
  zh-CN: 多选
  en-US: multiple selection
---

## zh-CN

多选，从已有条目中选择，例子中通过 `dwMaxTagCount` 限制最多显示3个选项。

## en-US

Multiple selection, selecting from existing items, max 3 option will display at the same time by `dwMaxTagCount`.
```
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'dw-demo-select-multiple',
  template: `
    <dw-select
      [dwMaxTagCount]="3"
      [dwMaxTagPlaceholder]="tagPlaceHolder"
      dwMode="multiple"
      dwPlaceHolder="Please select"
      [(ngModel)]="listOfSelectedValue"
    >
      <dw-option *ngFor="let item of listOfOption" [dwLabel]="item" [dwValue]="item"></dw-option>
    </dw-select>
    <ng-template #tagPlaceHolder let-selectedList> and {{ selectedList.length }} more selected </ng-template>
  `,
  styles: [
    `
      dw-select {
        width: 100%;
      }
    `
  ]
})
export class DwDemoSelectMultipleComponent implements OnInit {
  listOfOption: string[] = [];
  listOfSelectedValue = ['a10', 'c12'];

  ngOnInit(): void {
    const children: string[] = [];
    for (let i = 10; i < 36; i++) {
      children.push(`${i.toString(36)}${i}`);
    }
    this.listOfOption = children;
  }
}
```


---
order: 6
title:
  zh-CN: 分组
  en-US: Option Group
---

## zh-CN

用 `dw-option-group` 进行选项分组。

## en-US

Using `dw-option-group` to group the options.
```
import { Component } from '@angular/core';

@Component({
  selector: 'dw-demo-select-optgroup',
  template: `
    <dw-select [(ngModel)]="selectedValue" dwAllowClear dwPlaceHolder="Choose" dwShowSearch>
      <dw-option-group dwLabel="Manager">
        <dw-option dwValue="jack" dwLabel="Jack"></dw-option>
        <dw-option dwValue="lucy" dwLabel="Lucy"></dw-option>
      </dw-option-group>
      <dw-option-group dwLabel="Engineer">
        <dw-option dwValue="tom" dwLabel="Tom"></dw-option>
      </dw-option-group>
    </dw-select>
  `,
  styles: [
    `
      dw-select {
        width: 120px;
      }
    `
  ]
})
export class DwDemoSelectOptgroupComponent {
  selectedValue = 'lucy';
}
```


---
order: 23
title:
  zh-CN: 传入 Options
  en-US: Input Options
---

## zh-CN

通过 `dwOptions` 直接传入选项内容

## en-US

Pass all options via `dwOptions`
```
import { Component } from '@angular/core';

@Component({
  selector: 'dw-demo-select-options',
  template: `
    <dw-select ngModel="lucy" [dwOptions]="listOfOption"></dw-select>
    <dw-select [(ngModel)]="selectedValue" dwAllowClear dwPlaceHolder="Choose" [dwOptions]="listOfGroupOption"></dw-select>
  `,
  styles: [
    `
      dw-select {
        margin: 0 8px 10px 0;
        width: 120px;
      }
    `
  ]
})
export class DwDemoSelectOptionsComponent {
  selectedValue = 'lucy';
  listOfOption = [
    { label: 'Jack', value: 'jack' },
    { label: 'Lucy', value: 'lucy' },
    { label: 'disabled', value: 'disabled', disabled: true }
  ];
  listOfGroupOption = [
    { label: 'Jack', value: 'jack', groupLabel: 'Manager' },
    { label: 'Lucy', value: 'lucy', groupLabel: 'Manager' },
    { label: 'Tom', value: 'tom', groupLabel: 'Engineer' }
  ];
}
```


---
order: 17
title:
  zh-CN: 下拉加载
  en-US: Load Data on Scroll
---

## zh-CN

一个带有下拉加载远程数据的例子。

## en-US

Load data on scroll.
```
import { HttpClient } from '@angular/common/http';
import { Component, OnInit } from '@angular/core';
import { Observable } from 'rxjs';
import { map } from 'rxjs/operators';

@Component({
  selector: 'dw-demo-select-scroll-load',
  template: `
    <dw-select
      [(ngModel)]="selectedUser"
      (dwScrollToBottom)="loadMore()"
      dwPlaceHolder="Select users"
      dwAllowClear
      [dwDropdownRender]="renderTemplate"
    >
      <dw-option *ngFor="let o of optionList" [dwValue]="o" [dwLabel]="o"></dw-option>
    </dw-select>
    <ng-template #renderTemplate>
      <dw-spin *ngIf="isLoading"></dw-spin>
    </ng-template>
  `,
  styles: [
    `
      dw-select {
        width: 100%;
      }
    `
  ]
})
export class DwDemoSelectScrollLoadComponent implements OnInit {
  randomUserUrl = 'https://api.randomuser.me/?results=10';
  optionList: string[] = [];
  selectedUser = null;
  isLoading = false;
  // tslint:disable:no-any
  getRandomNameList: Observable<string[]> = this.http
    .get(`${this.randomUserUrl}`)
    .pipe(map((res: any) => res.results))
    .pipe(
      map((list: any) => {
        return list.map((item: any) => `${item.name.first}`);
      })
    );

  loadMore(): void {
    this.isLoading = true;
    this.getRandomNameList.subscribe(data => {
      this.isLoading = false;
      this.optionList = [...this.optionList, ...data];
    });
  }

  constructor(private http: HttpClient) {}

  ngOnInit(): void {
    this.loadMore();
  }
}
```


---
order: 9
title:
  zh-CN: 搜索框
  en-US: Search Box
---

## zh-CN

搜索和远程数据结合。

## en-US

Search with remote data.
```
import { HttpClient } from '@angular/common/http';
import { Component } from '@angular/core';

@Component({
  selector: 'dw-demo-select-search-box',
  template: `
    <dw-select
      dwShowSearch
      dwServerSearch
      dwPlaceHolder="input search text"
      [(ngModel)]="selectedValue"
      [dwShowArrow]="false"
      [dwFilterOption]="dwFilterOption"
      (dwOnSearch)="search($event)"
    >
      <dw-option *ngFor="let o of listOfOption" [dwLabel]="o.text" [dwValue]="o.value"> </dw-option>
    </dw-select>
  `,
  styles: [
    `
      dw-select {
        width: 200px;
      }
    `
  ]
})
export class DwDemoSelectSearchBoxComponent {
  selectedValue = null;
  listOfOption: Array<{ value: string; text: string }> = [];
  dwFilterOption = () => true;

  constructor(private httpClient: HttpClient) {}

  search(value: string): void {
    this.httpClient
      .jsonp<{ result: Array<[string, string]> }>(`https://suggest.taobao.com/sug?code=utf-8&q=${value}`, 'callback')
      .subscribe(data => {
        const listOfOption: Array<{ value: string; text: string }> = [];
        data.result.forEach(item => {
          listOfOption.push({
            value: item[0],
            text: item[0]
          });
        });
        this.listOfOption = listOfOption;
      });
  }
}
```


---
order: 1
title:
  zh-CN: 带搜索框
  en-US: Select with search field
---

## zh-CN

展开后可对选项进行搜索。

## en-US

Search the options while expanded.
```
import { Component } from '@angular/core';

@Component({
  selector: 'dw-demo-select-search',
  template: `
    <dw-select dwShowSearch dwAllowClear dwPlaceHolder="Select a person" [(ngModel)]="selectedValue">
      <dw-option dwLabel="Jack" dwValue="jack"></dw-option>
      <dw-option dwLabel="Lucy" dwValue="lucy"></dw-option>
      <dw-option dwLabel="Tom" dwValue="tom"></dw-option>
    </dw-select>
  `,
  styles: [
    `
      dw-select {
        width: 200px;
      }
    `
  ]
})
export class DwDemoSelectSearchComponent {
  selectedValue = null;
}
```


---
order: 13
title:
  zh-CN: 搜索用户
  en-US: Search and Select Users
---

## zh-CN

一个带有远程搜索，节流控制，请求时序控制，加载状态的多选示例。

## en-US

A complete multiple select sample with remote search, debounce fetch, ajax callback order flow, and loading state.
```
import { HttpClient } from '@angular/common/http';
import { Component, OnInit } from '@angular/core';
import { BehaviorSubject, Observable } from 'rxjs';
import { debounceTime, map, switchMap } from 'rxjs/operators';

@Component({
  selector: 'dw-demo-select-select-users',
  template: `
    <dw-select
      dwMode="multiple"
      dwPlaceHolder="Select users"
      dwAllowClear
      dwShowSearch
      dwServerSearch
      [(ngModel)]="selectedUser"
      (dwOnSearch)="onSearch($event)"
    >
      <ng-container *ngFor="let o of optionList">
        <dw-option *ngIf="!isLoading" [dwValue]="o" [dwLabel]="o"></dw-option>
      </ng-container>
      <dw-option *ngIf="isLoading" dwDisabled dwCustomContent>
        <i dw-icon dwType="loading" class="loading-icon"></i> Loading Data...
      </dw-option>
    </dw-select>
  `,
  styles: [
    `
      dw-select {
        width: 100%;
      }

      .loading-icon {
        margin-right: 8px;
      }
    `
  ]
})
export class DwDemoSelectSelectUsersComponent implements OnInit {
  randomUserUrl = 'https://api.randomuser.me/?results=5';
  searchChange$ = new BehaviorSubject('');
  optionList: string[] = [];
  selectedUser?: string;
  isLoading = false;

  onSearch(value: string): void {
    this.isLoading = true;
    this.searchChange$.next(value);
  }

  constructor(private http: HttpClient) {}

  ngOnInit(): void {
    // tslint:disable:no-any
    const getRandomNameList = (name: string) =>
      this.http
        .get(`${this.randomUserUrl}`)
        .pipe(map((res: any) => res.results))
        .pipe(
          map((list: any) => {
            return list.map((item: any) => `${item.name.first} ${name}`);
          })
        );
    const optionList$: Observable<string[]> = this.searchChange$
      .asObservable()
      .pipe(debounceTime(500))
      .pipe(switchMap(getRandomNameList));
    optionList$.subscribe(data => {
      this.optionList = data;
      this.isLoading = false;
    });
  }
}
```


---
order: 3
title:
  zh-CN: 三种大小
  en-US: Sizes
---

## zh-CN

三种大小的选择框，当 `dwSize` 分别为 `large` 和 `small` 时，输入框高度为 `40px` 和 `24px` ，默认高度为 `32px`。

## en-US

The height of the input field for the select defaults to 32px. If `dwSize` is set to large, the height will be 40px, and if set to small, 24px.
```
import { Component, OnInit } from '@angular/core';
import { DwSelectSizeType } from 'ng-zorro-antd/select';

@Component({
  selector: 'dw-demo-select-size',
  template: `
    <dw-radio-group [(ngModel)]="size">
      <label dw-radio-button dwValue="large"><span>Large</span></label>
      <label dw-radio-button dwValue="default"><span>Default</span></label>
      <label dw-radio-button dwValue="small"><span>Small</span></label>
    </dw-radio-group>
    <br /><br />
    <dw-select [(ngModel)]="singleValue" [dwSize]="size">
      <dw-option *ngFor="let option of listOfOption" [dwLabel]="option.label" [dwValue]="option.value"></dw-option>
    </dw-select>
    <br /><br />
    <dw-select [(ngModel)]="singleValue" [dwSize]="size" dwShowSearch>
      <dw-option *ngFor="let option of listOfOption" [dwLabel]="option.label" [dwValue]="option.value"></dw-option>
    </dw-select>
    <br /><br />
    <dw-select [(ngModel)]="multipleValue" [dwSize]="size" dwMode="multiple" dwPlaceHolder="Please select">
      <dw-option *ngFor="let option of listOfOption" [dwLabel]="option.label" [dwValue]="option.value"></dw-option>
    </dw-select>
    <br /><br />
    <dw-select [(ngModel)]="tagValue" [dwSize]="size" dwMode="tags" dwPlaceHolder="Please select">
      <dw-option *ngFor="let option of listOfOption" [dwLabel]="option.label" [dwValue]="option.value"></dw-option>
    </dw-select>
  `,
  styles: [
    `
      dw-select {
        width: 100%;
      }
    `
  ]
})
export class DwDemoSelectSizeComponent implements OnInit {
  listOfOption: Array<{ label: string; value: string }> = [];
  size: DwSelectSizeType = 'default';
  singleValue = 'a10';
  multipleValue = ['a10', 'c12'];
  tagValue = ['a10', 'c12', 'tag'];

  ngOnInit(): void {
    const children: Array<{ label: string; value: string }> = [];
    for (let i = 10; i < 36; i++) {
      children.push({ label: i.toString(36) + i, value: i.toString(36) + i });
    }
    this.listOfOption = children;
  }
}
```


---
order: 4
title:
  zh-CN: 标签
  en-US: Tags
---

## zh-CN

tags select，随意输入的内容（scroll the menu）

## en-US

Select with tags, transform input to tag (scroll the menu)
```
import { Component, OnInit } from '@angular/core';

@Component({
  selector: 'dw-demo-select-tags',
  template: `
    <dw-select dwMode="tags" dwPlaceHolder="Tag Mode" [(ngModel)]="listOfTagOptions">
      <dw-option *ngFor="let option of listOfOption" [dwLabel]="option.label" [dwValue]="option.value"></dw-option>
    </dw-select>
  `,
  styles: [
    `
      dw-select {
        width: 100%;
      }
    `
  ]
})
export class DwDemoSelectTagsComponent implements OnInit {
  listOfOption: Array<{ label: string; value: string }> = [];
  listOfTagOptions = [];

  ngOnInit(): void {
    const children: Array<{ label: string; value: string }> = [];
    for (let i = 10; i < 36; i++) {
      children.push({ label: i.toString(36) + i, value: i.toString(36) + i });
    }
    this.listOfOption = children;
  }
}
```


---
category: Components
type: 数据录入
title: DatePicker
subtitle: 日期选择框
---

输入或选择日期的控件。

## 何时使用

当用户需要输入一个日期，可以点击标准输入框，弹出日期面板进行选择。

```ts
import { DwDatePickerModule } from 'ng-zorro-antd/date-picker';
```

## API

**注意：**dw-date-picker 的部分 locale 来自于 Angular 自身的[国际化支持](https://angular.io/guide/i18n)，需要在 `app.module.ts` 文件中 引入相应的 Angular 语言包。
例如：
```typescript
import { registerLocaleData } from '@angular/common';
import zh from '@angular/common/locales/zh';
registerLocaleData(zh);
```

日期类组件包括以下五种形式。

- dw-date-picker
- dw-month-picker
- dw-range-picker
- dw-week-picker
- dw-year-picker

**注意：** 所有输入输出日期对象均为 [Date](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date)，你可以通过 [date-fns](https://date-fns.org/) 工具库获得你需要的数据。

### 共同的 API

以下 API 为 dw-date-picker、dw-month-picker、dw-range-picker, dw-week-picker 共享的 API。

| 参数 | 说明 | 类型 | 默认值 | 全局配置 |
| --- | --- | --- | --- | - |
| `[dwAllowClear]` | 是否显示清除按钮 | `boolean` | `true` | - |
| `[dwAutoFocus]` | 自动获取焦点 | `boolean` | `false` | - |
| `[dwDateRender]` | 自定义日期单元格的内容（month-picker/year-picker不支持） | `TemplateRef<Date> \| string \| ((d: Date) => TemplateRef<Date> \| string)` | - | - |
| `[dwDisabled]` | 禁用 | `boolean` | `false` | - |
| `[dwInputReadOnly]` | 为 input 标签设置只读属性（避免在移动设备上触发小键盘） | `boolean` | `false` | - |
| `[dwDisabledDate]` | 不可选择的日期 | `(current: Date) => boolean` | - | - |
| `[dwLocale]` | 国际化配置 | `object` | [默认配置](https://github.com/ant-design/ant-design/blob/master/components/date-picker/locale/example.json) | - |
| `[dwOpen]` | 控制弹层是否展开 | `boolean` | - | - |
| `[dwPopupStyle]` | 额外的弹出日历样式 | `object` | `{}` | - |
| `[dwDropdownClassName]` | 额外的弹出日历 className | `string` | - | - |
| `[dwSize]` | 输入框大小，`large` 高度为 40px，`small` 为 24px，默认是 32px | `'large' \| 'small'` | - | - |
| `[dwDefaultPickerValue]` | 默认面板日期 | `Date` \| `Date[]` | - | - |
| `[dwSuffixIcon]` | 自定义的后缀图标 | `string` \| `TemplateRef` | - | ✅ |
| `(dwOnOpenChange)` | 弹出日历和关闭日历的回调 | `EventEmitter<boolean>` | - | - |

### dw-date-picker

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| `[ngModel]` | 日期 | `Date` | - |
| `[dwDisabledTime]` | 不可选择的时间 | `(current: Date) => { dwDisabledHours, dwDisabledMinutes, dwDisabledSeconds }` | - |
| `[dwFormat]` | 展示的日期格式，见`dwFormat特别说明` | `string` | `'yyyy-MM-dd'` |
| `[dwRenderExtraFooter]` | 在面板中添加额外的页脚 | `TemplateRef \| string \| (() => TemplateRef \| string)` | - |
| `[dwShowTime]` | 增加时间选择功能 | `object \| boolean` | [TimePicker Options](/components/time-picker/zh#api) |
| `[dwShowToday]` | 是否展示“今天”按钮 | `boolean` | `true` |
| `[dwPlaceHolder]` | 输入框提示文字 | `string` | - |
| `(dwOnOk)` | 点击确定按钮的回调 | `EventEmitter<Date>` | - |
| `(ngModelChange)` | 时间发生变化的回调 | `EventEmitter<Date>` | - |

### dw-year-picker

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| `[ngModel]` | 日期 | `Date` | - |
| `[dwFormat]` | 展示的日期格式，见`dwFormat特别说明` | `string` | `'yyyy'` |
| `[dwRenderExtraFooter]` | 在面板中添加额外的页脚 | `TemplateRef \| string \| (() => TemplateRef \| string)` | - |
| `[dwPlaceHolder]` | 输入框提示文字 | `string` | - |
| `(ngModelChange)` | 时间发生变化的回调 | `EventEmitter<Date>` | - |

### dw-month-picker

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| `[ngModel]` | 日期 | `Date` | - |
| `[dwFormat]` | 展示的日期格式，见`dwFormat特别说明` | `string` | `'yyyy-MM'` |
| `[dwRenderExtraFooter]` | 在面板中添加额外的页脚 | `TemplateRef \| string \| (() => TemplateRef \| string)` | - |
| `[dwPlaceHolder]` | 输入框提示文字 | `string` | - |
| `(ngModelChange)` | 时间发生变化的回调 | `EventEmitter<Date>` | - |

### dw-week-picker

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| `[ngModel]` | 日期 | `Date` | - |
| `[dwFormat]` | 展示的日期格式，见`dwFormat特别说明` | `string` | `'yyyy-ww'` |
| `[dwPlaceHolder]` | 输入框提示文字 | `string` | - |
| `(ngModelChange)` | 时间发生变化的回调 | `EventEmitter<Date>` | - |

### dw-range-picker

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| `[ngModel]` | 日期 | `Date[]` | - |
| `[dwDisabledTime]` | 不可选择的时间 | `(current: Date, partial: 'start' \| 'end') => { dwDisabledHours, dwDisabledMinutes, dwDisabledSeconds }` | - |
| `[dwFormat]` | 展示的日期格式，见`dwFormat特别说明` | `string` | `'yyyy-MM-dd'` |
| `[dwRanges]` | 预设时间范围快捷选择 | `{ [ key: string ]: Date[] }  \|  { [ key: string ]: () => Date[] }` | - |
| `[dwRenderExtraFooter]` | 在面板中添加额外的页脚 | `TemplateRef \| string \| (() => TemplateRef \| string)` | - |
| `[dwShowTime]` | 增加时间选择功能 | `object \| boolean` | [TimePicker Options](/components/time-picker/zh#api) |
| `[dwPlaceHolder]` | 输入框提示文字 | `string[]` | - |
| `[dwSeparator]` | 分隔符 | `string` | `'~'` |
| `(dwOnOk)` | 点击确定按钮的回调 | `EventEmitter<Date[]>` | - |
| `(ngModelChange)` | 时间发生变化的回调 | `EventEmitter<Date[]>` | - |
| `(dwOnCalendarChange)` | 待选日期发生变化的回调 | `EventEmitter<Date[]>` | - |

> `dwShowTime` 中当前支持的 `dw-time-picker` 参数有：`dwFormat`, `dwHourStep`, `dwMinuteStep`, `dwSecondStep`, `dwDisabledHours`, `dwDisabledMinutes`, `dwDisabledSeconds`, `dwHideDisabledOptions`, `dwDefaultOpenValue`, `dwAddOn`

### dwFormat特别说明

日期格式化目前同时支持两种方式：`DatePipe`（默认，[语法参考](https://angular.io/api/common/DatePipe)） 和 `Date-fns`（[语法参考](https://date-fns.org/docs/format#description)，见[`如何使用Date-fns进行日期格式化`](/docs/i18n/zh#如何使用Date-fns进行日期格式化)）。

---
order: 0
title:
  zh-CN: 基本
  en-US: Basic
---

## zh-CN

最简单的用法，在浮层中可以选择或者输入日期。

## en-US

Basic use case. Users can select or input a date in panel.
```
import { Component } from '@angular/core';
import getISOWeek from 'date-fns/getISOWeek';
import { en_US, DwI18nService, zh_CN } from 'ng-zorro-antd/i18n';

@Component({
  selector: 'dw-demo-date-picker-basic',
  template: `
    <dw-date-picker [(ngModel)]="date" (ngModelChange)="onChange($event)"></dw-date-picker>
    <br />
    <dw-month-picker [(ngModel)]="date" (ngModelChange)="onChange($event)" dwPlaceHolder="Select month"></dw-month-picker>
    <br />
    <dw-year-picker [(ngModel)]="date" (ngModelChange)="onChange($event)" dwPlaceHolder="Select year"></dw-year-picker>
    <br />
    <dw-range-picker [(ngModel)]="dateRange" (ngModelChange)="onChange($event)"></dw-range-picker>
    <br />
    <dw-week-picker [(ngModel)]="date" (ngModelChange)="getWeek($event)" dwPlaceHolder="Select week"></dw-week-picker>
    <br />
    <button dw-button dwType="default" (click)="changeLanguage()">Switch language for all pickers</button>
  `,
  styles: [
    `
      dw-date-picker,
      dw-month-picker,
      dw-year-picker,
      dw-range-picker,
      dw-week-picker {
        margin: 0 8px 12px 0;
      }
    `
  ]
})
export class DwDemoDatePickerBasicComponent {
  date = null;
  dateRange = [];
  isEnglish = false;

  constructor(private i18n: DwI18nService) {}

  onChange(result: Date): void {
    console.log('onChange: ', result);
  }

  getWeek(result: Date): void {
    console.log('week: ', getISOWeek(result));
  }

  changeLanguage(): void {
    this.i18n.setLocale(this.isEnglish ? zh_CN : en_US);
    this.isEnglish = !this.isEnglish;
  }
}
```


---
order: 12
title:
  zh-CN: 定制日期单元格
  en-US: Customized Date Rendering
---

## zh-CN

使用 `dwDateRender` 可以自定义日期单元格的内容和样式。

## en-US

We can customize the rendering of date cells in the calendar by providing a `dwDateRender` function to `DatePicker`.
```
import { Component } from '@angular/core';

@Component({
  selector: 'dw-demo-date-picker-date-render',
  template: `
    <dw-date-picker [dwDateRender]="tplRender"></dw-date-picker>
    <dw-range-picker [dwDateRender]="tplRender"></dw-range-picker>

    <ng-template #tplRender let-current>
      <div class="ant-picker-cell-inner" [class.border]="current.getDate() === 1">
        {{ current.getDate() }}
      </div>
    </ng-template>
  `,
  styles: [
    `
      dw-date-picker,
      dw-month-picker,
      dw-range-picker,
      dw-week-picker {
        margin: 0 8px 12px 0;
      }
      .border {
        border: 1px solid #1890ff;
        border-radius: 50%;
      }
    `
  ]
})
export class DwDemoDatePickerDateRenderComponent {}
```


---
order: 6
title:
  zh-CN: 不可选择日期和时间
  en-US: Disabled Date & Time
---

## zh-CN

可用 `dwDisabledDate` 和 `dwDisabledTime` 分别禁止选择部分日期和时间。

## en-US

Disabled part of dates and time by `dwDisabledDate` and `dwDisabledTime` respectively.
```
import { Component } from '@angular/core';
import differenceInCalendarDays from 'date-fns/differenceInCalendarDays';
import setHours from 'date-fns/setHours';
import { DisabledTimeFn, DisabledTimePartial } from 'ng-zorro-antd/date-picker';

@Component({
  selector: 'dw-demo-date-picker-disabled-date',
  template: `
    <dw-date-picker
      dwFormat="yyyy-MM-dd HH:mm:ss"
      [dwDisabledDate]="disabledDate"
      [dwDisabledTime]="disabledDateTime"
      [dwShowTime]="{ dwDefaultOpenValue: timeDefaultValue }"
    >
    </dw-date-picker>
    <br />
    <dw-month-picker [dwDisabledDate]="disabledDate" dwPlaceHolder="Select month"></dw-month-picker>
    <br />
    <dw-year-picker [dwDisabledDate]="disabledDate" dwPlaceHolder="Select year"></dw-year-picker>
    <br />
    <dw-range-picker
      [dwDisabledDate]="disabledDate"
      [dwDisabledTime]="disabledRangeTime"
      [dwShowTime]="{ dwHideDisabledOptions: true, dwDefaultOpenValue: timeDefaultValue }"
      dwFormat="yyyy-MM-dd HH:mm:ss"
    ></dw-range-picker>
  `,
  styles: [
    `
      dw-date-picker,
      dw-month-picker,
      dw-year-picker,
      dw-range-picker,
      dw-week-picker {
        margin: 0 8px 12px 0;
      }
    `
  ]
})
export class DwDemoDatePickerDisabledDateComponent {
  today = new Date();
  timeDefaultValue = setHours(new Date(), 0);

  range(start: number, end: number): number[] {
    const result: number[] = [];
    for (let i = start; i < end; i++) {
      result.push(i);
    }
    return result;
  }

  disabledDate = (current: Date): boolean => {
    // Can not select days before today and today
    return differenceInCalendarDays(current, this.today) > 0;
  };

  disabledDateTime: DisabledTimeFn = () => {
    return {
      dwDisabledHours: () => this.range(0, 24).splice(4, 20),
      dwDisabledMinutes: () => this.range(30, 60),
      dwDisabledSeconds: () => [55, 56]
    };
  };

  disabledRangeTime: DisabledTimeFn = (_value, type?: DisabledTimePartial) => {
    if (type === 'start') {
      return {
        dwDisabledHours: () => this.range(0, 60).splice(4, 20),
        dwDisabledMinutes: () => this.range(30, 60),
        dwDisabledSeconds: () => [55, 56]
      };
    }
    return {
      dwDisabledHours: () => this.range(0, 60).splice(20, 4),
      dwDisabledMinutes: () => this.range(0, 31),
      dwDisabledSeconds: () => [55, 56]
    };
  };
}
```


---
order: 4
title:
  zh-CN: 禁用
  en-US: Disabled
---

## zh-CN

选择框的不可用状态。

## en-US

A disabled state of the `DatePicker`.
```
import { Component } from '@angular/core';

@Component({
  selector: 'dw-demo-date-picker-disabled',
  template: `
    <dw-date-picker dwDisabled></dw-date-picker>
    <br />
    <dw-month-picker dwDisabled></dw-month-picker>
    <br />
    <dw-range-picker dwDisabled></dw-range-picker>
  `,
  styles: [
    `
      dw-date-picker,
      dw-month-picker,
      dw-range-picker,
      dw-week-picker {
        margin: 0 8px 12px 0;
      }
    `
  ]
})
export class DwDemoDatePickerDisabledComponent {}
```


---
order: 10
title:
  zh-CN: 额外的页脚
  en-US: Extra Footer
---

## zh-CN

在浮层中加入额外的页脚，以满足某些定制信息的需求。

## en-US

Render extra footer in panel for customized requirements.
```
import { Component } from '@angular/core';

@Component({
  selector: 'dw-demo-date-picker-extra-footer',
  template: `
    <dw-date-picker [dwRenderExtraFooter]="footerRender"></dw-date-picker>
    <dw-date-picker [dwRenderExtraFooter]="plainFooter" dwShowTime></dw-date-picker>
    <dw-range-picker [dwRenderExtraFooter]="footerRender"></dw-range-picker>
    <dw-range-picker [dwRenderExtraFooter]="plainFooter" dwShowTime></dw-range-picker>
    <dw-month-picker [dwRenderExtraFooter]="footerRender" dwPlaceHolder="Select month"></dw-month-picker>
  `,
  styles: [
    `
      dw-date-picker,
      dw-month-picker,
      dw-range-picker,
      dw-week-picker {
        margin: 0 8px 12px 0;
      }
    `
  ]
})
export class DwDemoDatePickerExtraFooterComponent {
  plainFooter = 'plain extra footer';
  footerRender = () => 'extra footer';
}
```


---
order: 1
title:
  zh-CN: 日期格式
  en-US: Date Format
---

## zh-CN

使用 `dwFormat` 属性，可以自定义日期显示格式。

## en-US

We can set the date format by `dwFormat`.
```
import { Component } from '@angular/core';

@Component({
  selector: 'dw-demo-date-picker-format',
  template: `
    <dw-date-picker [dwFormat]="dateFormat"></dw-date-picker>
    <br />
    <dw-month-picker [dwFormat]="monthFormat" dwPlaceHolder="Select month"></dw-month-picker>
    <br />
    <dw-range-picker [dwFormat]="dateFormat"></dw-range-picker>
  `,
  styles: [
    `
      dw-date-picker,
      dw-month-picker,
      dw-range-picker,
      dw-week-picker {
        margin: 0 8px 12px 0;
      }
    `
  ]
})
export class DwDemoDatePickerFormatComponent {
  dateFormat = 'yyyy/MM/dd';
  monthFormat = 'yyyy/MM';
}
```


---
order: 11
title:
  zh-CN: 受控面板
  en-US: Controlled Panels
---

## zh-CN

通过组合 `dwMode` 与 `dwOnPanelChange` 控制要展示的面板。

## en-US

Determing which panel to show with `dwMode` and `dwOnPanelChange`.
```
import { Component } from '@angular/core';
import { DwDateMode } from 'ng-zorro-antd/date-picker';

@Component({
  selector: 'dw-demo-date-picker-mode',
  template: `
    <dw-date-picker
      [dwMode]="dateMode"
      dwShowTime
      (dwOnOpenChange)="handleDateOpenChange($event)"
      (dwOnPanelChange)="handleDatePanelChange($event)"
    >
    </dw-date-picker>
  `,
  styles: [
    `
      dw-date-picker,
      dw-month-picker,
      dw-range-picker,
      dw-week-picker {
        margin: 0 8px 12px 0;
      }
    `
  ]
})
export class DwDemoDatePickerModeComponent {
  dateMode: DwDateMode = 'time';

  handleDateOpenChange(open: boolean): void {
    if (open) {
      this.dateMode = 'time';
    }
  }

  handleDatePanelChange(mode: string | DwDateMode[] | string[]): void {
    console.log('handleDatePanelChange: ', mode);
  }
}
```


---
order: 8
title:
  zh-CN: 预设范围
  en-US: Presetted Ranges
---

## zh-CN

RangePicker 可以设置常用的 预设范围 提高用户体验。

## en-US

We can set presetted ranges to RangePicker to improve user experience.
```
import { Component } from '@angular/core';
import endOfMonth from 'date-fns/endOfMonth';

@Component({
  selector: 'dw-demo-date-picker-presetted-ranges',
  template: `
    <dw-range-picker [dwRanges]="ranges1" ngModel (ngModelChange)="onChange($event)"></dw-range-picker>
    <br />
    <dw-range-picker
      [dwRanges]="ranges1"
      dwShowTime
      dwFormat="yyyy/MM/dd HH:mm:ss"
      ngModel
      (ngModelChange)="onChange($event)"
    ></dw-range-picker>
  `,
  styles: [
    `
      dw-date-picker,
      dw-month-picker,
      dw-range-picker,
      dw-week-picker {
        margin: 0 8px 12px 0;
      }
    `
  ]
})
export class DwDemoDatePickerPresettedRangesComponent {
  ranges1 = { Today: [new Date(), new Date()], 'This Month': [new Date(), endOfMonth(new Date())] };
  ranges2 = { Today: [new Date(), new Date()], 'This Month': [new Date(), endOfMonth(new Date())] };

  onChange(result: Date[]): void {
    console.log('From: ', result[0], ', to: ', result[1]);
  }
}
```


---
order: 2
title:
  zh-CN: 三种大小
  en-US: Three Sizes
---

## zh-CN

三种大小的输入框，若不设置，则为 `default`。

## en-US

The input box comes in three sizes. `default` will be used if `dwSize` is omitted.
```
import { Component } from '@angular/core';

@Component({
  selector: 'dw-demo-date-picker-size',
  template: `
    <dw-radio-group [(ngModel)]="size">
      <label dw-radio-button dwValue="large">large</label>
      <label dw-radio-button dwValue="default">default</label>
      <label dw-radio-button dwValue="small">small</label>
    </dw-radio-group>
    <br /><br />
    <dw-date-picker [dwSize]="size"></dw-date-picker>
    <br />
    <dw-month-picker [dwSize]="size" dwPlaceHolder="Select Month"></dw-month-picker>
    <br />
    <dw-range-picker [dwSize]="size"></dw-range-picker>
    <br />
    <dw-week-picker [dwSize]="size" dwPlaceHolder="Select Week"></dw-week-picker>
  `,
  styles: [
    `
      dw-date-picker,
      dw-month-picker,
      dw-range-picker,
      dw-week-picker {
        margin: 0 8px 12px 0;
      }
    `
  ]
})
export class DwDemoDatePickerSizeComponent {
  size: 'large' | 'small' | 'default' = 'default';
}
```


---
order: 6
title:
  zh-CN: 自定义日期范围选择
  en-US: Customized Range Picker
---

## zh-CN

当 `RangePicker` 无法满足业务需求时，可以使用两个 `DatePicker` 实现类似的功能。
> * 通过设置 `dwDisabledDate` 方法，来约束开始和结束日期。
> * 通过 `dwOpen` `dwOnOpenChange` 来优化交互。

## en-US

When `RangePicker` does not satisfied your requirements, try to implement similar functionality with two `DatePicker`.
> * Use the `dwDisabledDate` property to limit the start and end dates.
> * Improve user experience with `dwOpen` and `dwOnOpenChange`.
```
import { Component } from '@angular/core';

@Component({
  selector: 'dw-demo-date-picker-start-end',
  template: `
    <dw-date-picker
      [dwDisabledDate]="disabledStartDate"
      dwShowTime
      dwFormat="yyyy-MM-dd HH:mm:ss"
      [(ngModel)]="startValue"
      dwPlaceHolder="Start"
      (ngModelChange)="onStartChange($event)"
      (dwOnOpenChange)="handleStartOpenChange($event)"
    >
    </dw-date-picker>
    <dw-date-picker
      [dwDisabledDate]="disabledEndDate"
      dwShowTime
      dwFormat="yyyy-MM-dd HH:mm:ss"
      [(ngModel)]="endValue"
      dwPlaceHolder="End"
      [dwOpen]="endOpen"
      (ngModelChange)="onEndChange($event)"
      (dwOnOpenChange)="handleEndOpenChange($event)"
    >
    </dw-date-picker>
  `,
  styles: [
    `
      dw-date-picker {
        margin: 0 8px 12px 0;
      }
    `
  ]
})
export class DwDemoDatePickerStartEndComponent {
  startValue: Date | null = null;
  endValue: Date | null = null;
  endOpen = false;

  disabledStartDate = (startValue: Date): boolean => {
    if (!startValue || !this.endValue) {
      return false;
    }
    return startValue.getTime() > this.endValue.getTime();
  };

  disabledEndDate = (endValue: Date): boolean => {
    if (!endValue || !this.startValue) {
      return false;
    }
    return endValue.getTime() <= this.startValue.getTime();
  };

  onStartChange(date: Date): void {
    this.startValue = date;
  }

  onEndChange(date: Date): void {
    this.endValue = date;
  }

  handleStartOpenChange(open: boolean): void {
    if (!open) {
      this.endOpen = true;
    }
    console.log('handleStartOpenChange', open, this.endOpen);
  }

  handleEndOpenChange(open: boolean): void {
    console.log(open);
    this.endOpen = open;
  }
}
```


---
order: 3
title:
  zh-CN: 日期时间选择
  en-US: Choose Time
---

## zh-CN

增加选择时间功能，当 `dwShowTime` 为一个对象时，其属性会传递给内建的 `TimePicker`。

## en-US

This property provide an additional time selection. When `dwShowTime` is an Object, its properties will be passed on to built-in `TimePicker`.
```
import { Component } from '@angular/core';

@Component({
  selector: 'dw-demo-date-picker-time',
  template: `
    <dw-date-picker
      dwShowTime
      dwFormat="yyyy-MM-dd HH:mm:ss"
      dwPlaceHolder="Select Time"
      ngModel
      (ngModelChange)="onChange($event)"
      (dwOnOk)="onOk($event)"
    ></dw-date-picker>
    <br />
    <dw-range-picker
      [dwShowTime]="{ dwFormat: 'HH:mm' }"
      dwFormat="yyyy-MM-dd HH:mm"
      [dwPlaceHolder]="['Start Time', 'End Time']"
      ngModel
      (ngModelChange)="onChange($event)"
      (dwOnOk)="onOk($event)"
    ></dw-range-picker>
  `,
  styles: [
    `
      dw-date-picker,
      dw-month-picker,
      dw-range-picker,
      dw-week-picker {
        margin: 0 8px 12px 0;
      }
    `
  ]
})
export class DwDemoDatePickerTimeComponent {
  onChange(result: Date): void {
    console.log('Selected Time: ', result);
  }

  onOk(result: Date | Date[] | null): void {
    console.log('onOk', result);
  }
}
```


---
category: Components
subtitle: 表单
type: 数据录入
cols: 1
title: Form
---

具有数据收集、校验和提交功能的表单，包含复选框、单选框、输入框、下拉选择框等元素。

该组件需要与 [Angular表单](https://angular.io/guide/forms#forms) 结合使用，开发者根据需要可以自由选择 [响应式表单](https://angular.io/guide/reactive-forms#reactive-forms) 或 [模板驱动表单](https://angular.io/guide/forms#template-driven-forms).
> 使用该组件前请确保您已经阅读并掌握了 [Forms](https://angular.io/guide/forms#forms) 的使用方式。

## 表单

我们提供了以下三种排列方式：

- 水平排列：标签和表单控件水平排列；（默认）
- 垂直排列：标签和表单控件上下垂直排列；
- 行内排列：表单项水平行内排列。

### 表单项 dw-form-item

表单项用于区分表单中不同的区域，包含表单域和表单标签(可选)。

### 表单标签 dw-form-label

用于标示当前表单项的内容，可选。

### 表单域 dw-form-control

表单一定会包含表单域，表单域可以是输入控件，标准表单域，标签，下拉菜单，文本域等。

```html
<form dw-form>
  <dw-form-item>
    <dw-form-label [dwSpan]="6" dwFor="email">E-mail</dw-form-label>
    <dw-form-control [dwSpan]="14">
      <input dw-input name="email" type="email" id="email">
    </dw-form-control>
  </dw-form-item >
</form>
```

```ts
import { DwFormModule } from 'ng-zorro-antd/form';
```

## API

### [dw-form]

| 参数 | 说明 | 类型 | 默认值 | 全局配置 |
| --- | --- | --- | --- | --- |
| `[dwLayout]`| 表单布局 | `'horizontal' \| 'vertical' \| 'inline'` | `'horizontal'` |
| `[dwNoColon]`| 配置 `dw-form-label` 的 `[dwNoColon]` 的默认值 | `boolean` | `false` | ✅ |
| `[dwAutoTips]`| 配置 `dw-form-control` 的 `[dwAutoTips]` 的默认值, 具体用法请参考示例：**自动提示** | `Record<string, Record<string, string>>` | `{}` | ✅ |
| `[dwDisableAutoTips]`| 配置 `dw-form-control` 的 `[dwDisableAutoTips]` 的默认值 | `boolean` | `false` | ✅ |

### dw-form-item

表单项用于区分表单中不同的区域，包含表单域和表单标签(可选)。

> 所有 [dw-row](/components/grid/zh) 的参数在 `dw-form-item` 上均可直接使用。

### dw-form-label

用于标示当前表单项的内容，可选。

> 所有 [dw-col](/components/grid/zh) 的参数在 `dw-form-label` 上均可直接使用。

| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| `[dwRequired]`| 当前项是否为必填，仅影响样式 | `boolean` | `false` |
| `[dwNoColon]`| 是否不显示 label 后面的冒号 | `boolean` | `false` |
| `[dwFor]`| label 标签的 for 属性	 | `string` | - |

### dw-form-control

> 注意：由于 Angular Form 目前提供的[状态变更订阅](https://github.com/angular/angular/issues/10887)不完整。手动更改表单状态时，例如 `markAsDirty` 后，需要执行 `updateValueAndValidity` 通知 `dw-form-control` 进行状态变更。

表单一定会包含表单域，表单域可以是输入控件，标准表单域，标签，下拉菜单，文本域等。

> 所有 [dw-col](/components/grid/zh) 的参数在 `dw-form-control` 上均可直接使用。


| 参数 | 说明 | 类型 | 默认值 |
| --- | --- | --- | --- |
| `[dwValidateStatus]` | 会根据传入的 `FormControl` 或 `NgModel` 自动生成校验状态，也可以直接指定状态，不传入时默认值为 `dw-form-control` 中包裹的第一个 `FormControl` 或 `NgModel` | `'success' \| 'warning' \| 'error' \| 'validating'  \|  FormControl  \|  NgModel` | `dw-form-control` 中包裹的第一个 `FormControl` 或 `NgModel`  |
| `[dwHasFeedback]`| 配合 `dwValidateStatus` 属性使用，展示校验状态图标	 | `boolean` | `false`|
| `[dwExtra]`| 用于显示表单额外提示信息 | `string  \|  TemplateRef<void>` | - |
| `[dwSuccessTip]`| 校验状态 success 时提示信息 | `string  \|  TemplateRef<{ $implicit: FormControl  \|  NgModel }>` | - |
| `[dwWarningTip]`| 校验状态 warning 时提示信息 | `string  \|  TemplateRef<{ $implicit: FormControl  \|  NgModel }>` | - |
| `[dwErrorTip]`| 校验状态 error 时提示信息 | `string  \|  TemplateRef<{ $implicit: FormControl  \|  NgModel }>` | - |
| `[dwValidatingTip]`| 正在校验时提示信息 | `string  \|  TemplateRef<{ $implicit: FormControl  \|  NgModel }>` | - |
| `[dwAutoTips]`| 配置提示的对象, 具体用法请参考示例：**自动提示** | `Record<string, Record<string, string>>` | - | - |
| `[dwDisableAutoTips]`| 禁用自动提示 | `boolean` | - | - |

### dw-form-split

用于显示分隔符 `-`

### dw-form-text

在 `dw-form-control` 中直接显示文本

---
order: 3
title:
  zh-CN: 高级搜索
  en-US: Advanced search
---

## zh-CN

三列栅格式的表单排列方式，常用于数据表格的高级搜索。

有部分定制的样式代码，由于输入标签长度不确定，需要根据具体情况自行调整。

## en-US

Three columns layout is often used for advanced searching of data table.

Because the width of label is not fixed, you may need to adjust it by customizing its style.
```
import { Component, OnInit } from '@angular/core';
import { FormBuilder, FormControl, FormGroup } from '@angular/forms';

@Component({
  selector: 'dw-demo-form-advanced-search',
  template: `
    <form dw-form [formGroup]="validateForm" class="ant-advanced-search-form">
      <div dw-row [dwGutter]="24">
        <div dw-col [dwSpan]="8" *ngFor="let control of controlArray" [hidden]="!control.show">
          <dw-form-item>
            <dw-form-label [dwFor]="'field' + control.index">Field {{ control.index }}</dw-form-label>
            <dw-form-control>
              <input dw-input placeholder="placeholder" [formControlName]="'field' + control.index" [attr.id]="'field' + control.index" />
            </dw-form-control>
          </dw-form-item>
        </div>
      </div>
      <div dw-row>
        <div dw-col [dwSpan]="24" class="search-area">
          <button dw-button [dwType]="'primary'">Search</button>
          <button dw-button (click)="resetForm()">Clear</button>
          <a class="collapse" (click)="toggleCollapse()">
            Collapse
            <i dw-icon [dwType]="isCollapse ? 'down' : 'up'"></i>
          </a>
        </div>
      </div>
    </form>
    <div class="search-result-list">
      Search Result List
    </div>
  `,

  styles: [
    `
      .ant-advanced-search-form {
        padding: 24px;
        background: #fbfbfb;
        border: 1px solid #d9d9d9;
        border-radius: 6px;
      }

      .search-result-list {
        margin-top: 16px;
        border: 1px dashed #e9e9e9;
        border-radius: 6px;
        background-color: #fafafa;
        min-height: 200px;
        text-align: center;
        padding-top: 80px;
      }

      [dw-form-label] {
        overflow: visible;
      }

      button {
        margin-left: 8px;
      }

      .collapse {
        margin-left: 8px;
        font-size: 12px;
      }

      .search-area {
        text-align: right;
      }
    `
  ]
})
export class DwDemoFormAdvancedSearchComponent implements OnInit {
  validateForm!: FormGroup;
  controlArray: Array<{ index: number; show: boolean }> = [];
  isCollapse = true;

  toggleCollapse(): void {
    this.isCollapse = !this.isCollapse;
    this.controlArray.forEach((c, index) => {
      c.show = this.isCollapse ? index < 6 : true;
    });
  }

  resetForm(): void {
    this.validateForm.reset();
  }

  constructor(private fb: FormBuilder) {}

  ngOnInit(): void {
    this.validateForm = this.fb.group({});
    for (let i = 0; i < 10; i++) {
      this.controlArray.push({ index: i, show: i < 6 });
      this.validateForm.addControl(`field${i}`, new FormControl());
    }
  }
}
```


---
order: 11
title:
  zh-CN: 自动提示
  en-US: Auto tips
---

## zh-CN

让提示变得更简单。  
需要预先自定义 `Validators` 和提供 `dwAutoTips`，它们优先级如下：

- `Validators` > `dwAutoTips`
- 通过 `@Input` 设置 `dwAutoTips`
- 通过全局配置设置 `dwAutoTips`

另外，你可以使用 `dwDisableAutoTips` 去禁用它。

## en-US

Make tips to be easy.  
Need to customize `Validators` and provide `dwAutoTips` in advance, the priority is as follows:

- `Validators` > `dwAutoTips`
- Via `@Input` set `dwAutoTips`
- Via global config set `dwAutoTips`

In addition, you can use `dwDisableAutoTips` to disable it.
```
import { Component } from '@angular/core';
import { AbstractControl, FormBuilder, FormControl, FormGroup, ValidatorFn, Validators } from '@angular/forms';
import { DwSafeAny } from 'ng-zorro-antd/core/types';
import { Observable, Observer } from 'rxjs';

@Component({
  selector: 'dw-demo-form-auto-tips',
  template: `
    <form dw-form [dwAutoTips]="autoTips" [formGroup]="validateForm" (ngSubmit)="submitForm(validateForm.value)">
      <dw-form-item>
        <dw-form-label [dwSpan]="7" dwRequired>Username</dw-form-label>
        <dw-form-control [dwSpan]="12" dwValidatingTip="Validating...">
          <input dw-input formControlName="userName" placeholder="async validate try to write JasonWood" />
        </dw-form-control>
      </dw-form-item>
      <dw-form-item>
        <dw-form-label [dwSpan]="7" dwRequired>Mobile</dw-form-label>
        <dw-form-control [dwSpan]="12">
          <input dw-input formControlName="mobile" placeholder="mobile" />
        </dw-form-control>
      </dw-form-item>
      <dw-form-item>
        <dw-form-label [dwSpan]="7" dwRequired>E-mail</dw-form-label>
        <dw-form-control [dwSpan]="12">
          <input dw-input formControlName="email" placeholder="email" type="email" />
        </dw-form-control>
      </dw-form-item>
      <dw-form-item>
        <dw-form-label [dwSpan]="7" dwRequired>Password</dw-form-label>
        <dw-form-control [dwSpan]="12" dwDisableAutoTips dwErrorTip="Please input your password!">
          <input dw-input type="password" formControlName="password" (ngModelChange)="validateConfirmPassword()" />
        </dw-form-control>
      </dw-form-item>
      <dw-form-item>
        <dw-form-label [dwSpan]="7" dwRequired>Confirm Password</dw-form-label>
        <dw-form-control [dwSpan]="12" dwDisableAutoTips [dwErrorTip]="passwordErrorTpl">
          <input dw-input type="password" formControlName="confirm" placeholder="confirm your password" />
          <ng-template #passwordErrorTpl let-control>
            <ng-container *ngIf="control.hasError('required')">
              Please confirm your password!
            </ng-container>
            <ng-container *ngIf="control.hasError('confirm')">
              Password is inconsistent!
            </ng-container>
          </ng-template>
        </dw-form-control>
      </dw-form-item>
      <dw-form-item>
        <dw-form-control [dwOffset]="7" [dwSpan]="12">
          <button dw-button dwType="primary">Submit</button>
        </dw-form-control>
      </dw-form-item>
    </form>
  `,
  styles: [
    `
      [dw-form] {
        max-width: 600px;
      }
    `
  ]
})
export class DwDemoFormAutoTipsComponent {
  validateForm: FormGroup;

  // current locale is key of the dwAutoTips
  autoTips: Record<string, Record<string, string>> = {
    'zh-cn': {
      required: '必填项',
      email: '邮箱格式不正确'
    },
    en: {
      required: 'Input is required',
      email: 'The input is not valid email'
    }
  };

  submitForm(value: { userName: string; email: string; password: string; confirm: string; comment: string }): void {
    for (const key in this.validateForm.controls) {
      this.validateForm.controls[key].markAsDirty();
      this.validateForm.controls[key].updateValueAndValidity();
    }
    console.log(value);
  }

  validateConfirmPassword(): void {
    setTimeout(() => this.validateForm.controls.confirm.updateValueAndValidity());
  }

  userNameAsyncValidator = (control: FormControl) =>
    new Observable((observer: Observer<MyValidationErrors | null>) => {
      setTimeout(() => {
        if (control.value === 'JasonWood') {
          observer.next({
            duplicated: { 'zh-cn': `用户名已存在`, en: `The username is redundant!` }
          });
        } else {
          observer.next(null);
        }
        observer.complete();
      }, 1000);
    });

  confirmValidator = (control: FormControl): { [s: string]: boolean } => {
    if (!control.value) {
      return { error: true, required: true };
    } else if (control.value !== this.validateForm.controls.password.value) {
      return { confirm: true, error: true };
    }
    return {};
  };

  constructor(private fb: FormBuilder) {
    // use `MyValidators`
    const { required, maxLength, minLength, email, mobile } = MyValidators;
    this.validateForm = this.fb.group({
      userName: ['', [required, maxLength(12), minLength(6)], [this.userNameAsyncValidator]],
      mobile: ['', [required, mobile]],
      email: ['', [required, email]],
      password: ['', [required]],
      confirm: ['', [this.confirmValidator]]
    });
  }
}

// current locale is key of the MyErrorsOptions
export type MyErrorsOptions = { 'zh-cn': string; en: string } & Record<string, DwSafeAny>;
export type MyValidationErrors = Record<string, MyErrorsOptions>;

export class MyValidators extends Validators {
  static minLength(minLength: number): ValidatorFn {
    return (control: AbstractControl): MyValidationErrors | null => {
      if (Validators.minLength(minLength)(control) === null) {
        return null;
      }
      return { minlength: { 'zh-cn': `最小长度为 ${minLength}`, en: `MinLength is ${minLength}` } };
    };
  }

  static maxLength(maxLength: number): ValidatorFn {
    return (control: AbstractControl): MyValidationErrors | null => {
      if (Validators.maxLength(maxLength)(control) === null) {
        return null;
      }
      return { maxlength: { 'zh-cn': `最大长度为 ${maxLength}`, en: `MaxLength is ${maxLength}` } };
    };
  }

  static mobile(control: AbstractControl): MyValidationErrors | null {
    const value = control.value;

    if (isEmptyInputValue(value)) {
      return null;
    }

    return isMobile(value) ? null : { mobile: { 'zh-cn': `手机号码格式不正确`, en: `Mobile phone number is not valid` } };
  }
}

function isEmptyInputValue(value: DwSafeAny): boolean {
  return value == null || value.length === 0;
}

function isMobile(value: string): boolean {
  return typeof value === 'string' && /(^1\d{10}$)/.test(value);
}
```

---
order: 12
title:
  zh-CN: 表单联动
  en-US: Coordinated Controls
---

## zh-CN

使用 `setValue` 来动态设置其他控件的值。

## en-US

Use `setValue` to set other control's value programmaticly.
```
import { Component, OnInit } from '@angular/core';
import { FormBuilder, FormGroup, Validators } from '@angular/forms';

@Component({
  selector: 'dw-demo-form-coordinated',
  template: `
    <form dw-form [formGroup]="validateForm" (ngSubmit)="submitForm()">
      <dw-form-item>
        <dw-form-label [dwSpan]="5" dwRequired dwFor="note">Note</dw-form-label>
        <dw-form-control [dwSpan]="12" dwErrorTip="Please input your username!">
          <input id="note" type="text" dw-input formControlName="note" />
        </dw-form-control>
      </dw-form-item>
      <dw-form-item>
        <dw-form-label [dwSpan]="5" dwFor="gender" dwRequired>Gender</dw-form-label>
        <dw-form-control [dwSpan]="12" dwErrorTip="Please select your gender!">
          <dw-select
            id="gender"
            formControlName="gender"
            dwPlaceHolder="Select a option and change input text above"
            (ngModelChange)="genderChange($event)"
          >
            <dw-option dwValue="male" dwLabel="male"></dw-option>
            <dw-option dwValue="female" dwLabel="female"></dw-option>
          </dw-select>
        </dw-form-control>
      </dw-form-item>
      <dw-form-item>
        <dw-form-control [dwSpan]="12" [dwOffset]="5">
          <button dw-button dwType="primary">Submit</button>
        </dw-form-control>
      </dw-form-item>
    </form>
  `,
  styles: [
    `
      [dw-form] {
        max-width: 600px;
      }
    `
  ]
})
export class DwDemoFormCoordinatedComponent implements OnInit {
  validateForm!: FormGroup;

  submitForm(): void {
    for (const i in this.validateForm.controls) {
      this.validateForm.controls[i].markAsDirty();
      this.validateForm.controls[i].updateValueAndValidity();
    }
  }

  genderChange(value: string): void {
    this.validateForm.get('note')!.setValue(value === 'male' ? 'Hi, man!' : 'Hi, lady!');
  }

  constructor(private fb: FormBuilder) {}

  ngOnInit(): void {
    this.validateForm = this.fb.group({
      note: [null, [Validators.required]],
      gender: [null, [Validators.required]]
    });
  }
}
```


---
order: 5
title:
  zh-CN: 动态增减表单项
  en-US: Dynamic Form Item
---

## zh-CN

动态增加、减少表单项。

## en-US

Add or remove form items dynamically.
```
import { Component, OnInit } from '@angular/core';
import { FormBuilder, FormControl, FormGroup, Validators } from '@angular/forms';

@Component({
  selector: 'dw-demo-form-dynamic-form-item',
  template: `
    <form dw-form [formGroup]="validateForm" (ngSubmit)="submitForm()">
      <dw-form-item *ngFor="let control of listOfControl; let i = index">
        <dw-form-label [dwXs]="24" [dwSm]="4" *ngIf="i == 0" [dwFor]="control.controlInstance">Passengers </dw-form-label>
        <dw-form-control
          [dwXs]="24"
          [dwSm]="20"
          [dwOffset]="i == 0 ? 0 : 4"
          dwErrorTip="Please input passenger's name or delete this field."
        >
          <input
            class="passenger-input"
            dw-input
            placeholder="placeholder"
            [attr.id]="control.id"
            [formControlName]="control.controlInstance"
          />
          <i dw-icon dwType="minus-circle-o" class="dynamic-delete-button" (click)="removeField(control, $event)"></i>
        </dw-form-control>
      </dw-form-item>
      <dw-form-item>
        <dw-form-control [dwXs]="{ span: 24, offset: 0 }" [dwSm]="{ span: 20, offset: 4 }">
          <button dw-button dwType="dashed" class="add-button" (click)="addField($event)">
            <i dw-icon dwType="plus"></i>
            Add field
          </button>
        </dw-form-control>
      </dw-form-item>
      <dw-form-item>
        <dw-form-control [dwXs]="{ span: 24, offset: 0 }" [dwSm]="{ span: 20, offset: 4 }">
          <button dw-button dwType="primary">Submit</button>
        </dw-form-control>
      </dw-form-item>
    </form>
  `,

  styles: [
    `
      .dynamic-delete-button {
        cursor: pointer;
        position: relative;
        top: 4px;
        font-size: 24px;
        color: #999;
        transition: all 0.3s;
      }

      .dynamic-delete-button:hover {
        color: #777;
      }

      .passenger-input {
        width: 60%;
        margin-right: 8px;
      }

      [dw-form] {
        max-width: 600px;
      }

      .add-button {
        width: 60%;
      }
    `
  ]
})
export class DwDemoFormDynamicFormItemComponent implements OnInit {
  validateForm!: FormGroup;
  listOfControl: Array<{ id: number; controlInstance: string }> = [];

  addField(e?: MouseEvent): void {
    if (e) {
      e.preventDefault();
    }
    const id = this.listOfControl.length > 0 ? this.listOfControl[this.listOfControl.length - 1].id + 1 : 0;

    const control = {
      id,
      controlInstance: `passenger${id}`
    };
    const index = this.listOfControl.push(control);
    console.log(this.listOfControl[this.listOfControl.length - 1]);
    this.validateForm.addControl(this.listOfControl[index - 1].controlInstance, new FormControl(null, Validators.required));
  }

  removeField(i: { id: number; controlInstance: string }, e: MouseEvent): void {
    e.preventDefault();
    if (this.listOfControl.length > 1) {
      const index = this.listOfControl.indexOf(i);
      this.listOfControl.splice(index, 1);
      console.log(this.listOfControl);
      this.validateForm.removeControl(i.controlInstance);
    }
  }

  submitForm(): void {
    for (const i in this.validateForm.controls) {
      this.validateForm.controls[i].markAsDirty();
      this.validateForm.controls[i].updateValueAndValidity();
    }
    console.log(this.validateForm.value);
  }

  constructor(private fb: FormBuilder) {}

  ngOnInit(): void {
    this.validateForm = this.fb.group({});
    this.addField();
  }
}
```


---
order: 13
title:
  zh-CN: 动态校验规则
  en-US: Dynamic Rules
---

## zh-CN

根据不同情况执行不同的校验规则。

## en-US

Perform different check rules according to different situations.
```
import { Component, OnInit } from '@angular/core';
import { FormBuilder, FormGroup, Validators } from '@angular/forms';

@Component({
  selector: 'dw-demo-form-dynamic-rule',
  template: `
    <form dw-form [formGroup]="validateForm" (ngSubmit)="submitForm()">
      <dw-form-item>
        <dw-form-label [dwSpan]="4" dwRequired dwFor="name">Name</dw-form-label>
        <dw-form-control [dwSpan]="8" dwErrorTip="Please input your name">
          <input type="text" dw-input formControlName="name" placeholder="Please input your name" />
        </dw-form-control>
      </dw-form-item>
      <dw-form-item>
        <dw-form-label [dwSpan]="4" dwFor="nickname" [dwRequired]="validateForm.get('required')?.value">Nickname</dw-form-label>
        <dw-form-control [dwSpan]="8" dwErrorTip="Please input your nickname">
          <input type="text" dw-input formControlName="nickname" placeholder="Please input your nickname" />
        </dw-form-control>
      </dw-form-item>
      <dw-form-item>
        <dw-form-control [dwSpan]="8" [dwOffset]="4">
          <label dw-checkbox formControlName="required" (ngModelChange)="requiredChange($event)">Nickname is required</label>
        </dw-form-control>
      </dw-form-item>
      <dw-form-item>
        <dw-form-control [dwSpan]="8" [dwOffset]="4">
          <button dw-button dwType="primary">Check</button>
        </dw-form-control>
      </dw-form-item>
    </form>
  `
})
export class DwDemoFormDynamicRuleComponent implements OnInit {
  validateForm!: FormGroup;

  submitForm(): void {
    for (const i in this.validateForm.controls) {
      this.validateForm.controls[i].markAsDirty();
      this.validateForm.controls[i].updateValueAndValidity();
    }
  }

  requiredChange(required: boolean): void {
    if (!required) {
      this.validateForm.get('nickname')!.clearValidators();
      this.validateForm.get('nickname')!.markAsPristine();
    } else {
      this.validateForm.get('nickname')!.setValidators(Validators.required);
      this.validateForm.get('nickname')!.markAsDirty();
    }
    this.validateForm.get('nickname')!.updateValueAndValidity();
  }

  constructor(private fb: FormBuilder) {}

  ngOnInit(): void {
    this.validateForm = this.fb.group({
      name: [null, [Validators.required]],
      nickname: [null],
      required: [false]
    });
  }
}
```


---
order: 0
title:
  zh-CN: 内联登录栏
  en-US: Inline Login Form
---

## zh-CN

内联登录栏，常用在顶部导航栏中。

## en-US

Inline login form is often used in navigation bar.
```
import { Component, OnInit } from '@angular/core';
import { FormBuilder, FormGroup, Validators } from '@angular/forms';

@Component({
  selector: 'dw-demo-form-horizontal-login',
  template: `
    <form dw-form [dwLayout]="'inline'" [formGroup]="validateForm" (ngSubmit)="submitForm()">
      <dw-form-item>
        <dw-form-control dwErrorTip="Please input your username!">
          <dw-input-group dwPrefixIcon="user">
            <input formControlName="userName" dw-input placeholder="Username" />
          </dw-input-group>
        </dw-form-control>
      </dw-form-item>
      <dw-form-item>
        <dw-form-control dwErrorTip="Please input your Password!">
          <dw-input-group dwPrefixIcon="lock">
            <input formControlName="password" dw-input type="password" placeholder="Password" />
          </dw-input-group>
        </dw-form-control>
      </dw-form-item>
      <dw-form-item>
        <dw-form-control>
          <button dw-button dwType="primary" [disabled]="!validateForm.valid">Log in</button>
        </dw-form-control>
      </dw-form-item>
    </form>
  `
})
export class DwDemoFormHorizontalLoginComponent implements OnInit {
  validateForm!: FormGroup;

  submitForm(): void {
    for (const i in this.validateForm.controls) {
      this.validateForm.controls[i].markAsDirty();
      this.validateForm.controls[i].updateValueAndValidity();
    }
  }

  constructor(private fb: FormBuilder) {}

  ngOnInit(): void {
    this.validateForm = this.fb.group({
      userName: [null, [Validators.required]],
      password: [null, [Validators.required]],
      remember: [true]
    });
  }
}
```


---
order: 12
title:
  zh-CN: 表单布局
  en-US: Form Layout
---

## zh-CN

表单有三种布局。

## en-US

There are three layout for form: `horizontal`, `vertical`, `inline`.
```
import { Component, OnInit } from '@angular/core';
import { FormBuilder, FormGroup, Validators } from '@angular/forms';

@Component({
  selector: 'dw-demo-form-layout',
  template: `
    <form dw-form [dwLayout]="validateForm.get('formLayout')?.value" [formGroup]="validateForm" (ngSubmit)="submitForm()">
      <dw-form-item>
        <dw-form-label [dwSpan]="isHorizontal ? 4 : null">Form Layout</dw-form-label>
        <dw-form-control [dwSpan]="isHorizontal ? 14 : null">
          <dw-radio-group formControlName="formLayout">
            <label dw-radio-button [dwValue]="'horizontal'">Horizontal</label>
            <label dw-radio-button [dwValue]="'vertical'">Vertical</label>
            <label dw-radio-button [dwValue]="'inline'">Inline</label>
          </dw-radio-group>
        </dw-form-control>
      </dw-form-item>
      <dw-form-item>
        <dw-form-label [dwSpan]="isHorizontal ? 4 : null">Field A</dw-form-label>
        <dw-form-control [dwSpan]="isHorizontal ? 14 : null" dwErrorTip="Please input your username!">
          <input dw-input formControlName="fieldA" placeholder="input placeholder" />
        </dw-form-control>
      </dw-form-item>
      <dw-form-item>
        <dw-form-label [dwSpan]="isHorizontal ? 4 : null">Field B</dw-form-label>
        <dw-form-control [dwSpan]="isHorizontal ? 14 : null" dwErrorTip="Please input your Password!">
          <input dw-input formControlName="filedB" placeholder="input placeholder" />
        </dw-form-control>
      </dw-form-item>
      <dw-form-item>
        <dw-form-control [dwSpan]="isHorizontal ? 14 : null" [dwOffset]="isHorizontal ? 4 : null">
          <button dw-button dwType="primary">Submit</button>
        </dw-form-control>
      </dw-form-item>
    </form>
  `,
  styles: [
    `
      [dw-form]:not(.ant-form-inline):not(.ant-form-vertical) {
        max-width: 600px;
      }
    `
  ]
})
export class DwDemoFormLayoutComponent implements OnInit {
  validateForm!: FormGroup;

  submitForm(): void {
    for (const i in this.validateForm.controls) {
      this.validateForm.controls[i].markAsDirty();
      this.validateForm.controls[i].updateValueAndValidity();
    }
  }

  get isHorizontal(): boolean {
    return this.validateForm.controls.formLayout?.value === 'horizontal';
  }

  constructor(private fb: FormBuilder) {}

  ngOnInit(): void {
    this.validateForm = this.fb.group({
      formLayout: ['horizontal'],
      fieldA: [null, [Validators.required]],
      filedB: [null, [Validators.required]]
    });
  }
}
```


---
order: 1
title:
  zh-CN: 登录框
  en-US: Login Form
---

## zh-CN

普通的登录框，可以容纳更多的元素。

## en-US

Normal login form which can contain more elements.
```
import { Component, OnInit } from '@angular/core';
import { FormBuilder, FormGroup, Validators } from '@angular/forms';

@Component({
  selector: 'dw-demo-form-normal-login',
  template: `
    <form dw-form [formGroup]="validateForm" class="login-form" (ngSubmit)="submitForm()">
      <dw-form-item>
        <dw-form-control dwErrorTip="Please input your username!">
          <dw-input-group dwPrefixIcon="user">
            <input type="text" dw-input formControlName="userName" placeholder="Username" />
          </dw-input-group>
        </dw-form-control>
      </dw-form-item>
      <dw-form-item>
        <dw-form-control dwErrorTip="Please input your Password!">
          <dw-input-group dwPrefixIcon="lock">
            <input type="password" dw-input formControlName="password" placeholder="Password" />
          </dw-input-group>
        </dw-form-control>
      </dw-form-item>
      <div dw-row class="login-form-margin">
        <div dw-col [dwSpan]="12">
          <label dw-checkbox formControlName="remember">
            <span>Remember me</span>
          </label>
        </div>
        <div dw-col [dwSpan]="12">
          <a class="login-form-forgot">Forgot password</a>
        </div>
      </div>
      <button dw-button class="login-form-button login-form-margin" [dwType]="'primary'">Log in</button>
      Or <a> register now! </a>
    </form>
  `,
  styles: [
    `
      .login-form {
        max-width: 300px;
      }

      .login-form-margin {
        margin-bottom: 16px;
      }

      .login-form-forgot {
        float: right;
      }

      .login-form-button {
        width: 100%;
      }
    `
  ]
})
export class DwDemoFormNormalLoginComponent implements OnInit {
  validateForm!: FormGroup;

  submitForm(): void {
    for (const i in this.validateForm.controls) {
      this.validateForm.controls[i].markAsDirty();
      this.validateForm.controls[i].updateValueAndValidity();
    }
  }

  constructor(private fb: FormBuilder) {}

  ngOnInit(): void {
    this.validateForm = this.fb.group({
      userName: [null, [Validators.required]],
      password: [null, [Validators.required]],
      remember: [true]
    });
  }
}
```


---
order: 2
title:
  zh-CN: 注册新用户
  en-US: Registration
---

## zh-CN

用户填写必须的信息以注册新用户。

## en-US

Fill in this form to create a new account for you.
```
import { Component, OnInit } from '@angular/core';
import { FormBuilder, FormControl, FormGroup, Validators } from '@angular/forms';

@Component({
  selector: 'dw-demo-form-register',
  template: `
    <form dw-form [formGroup]="validateForm" (ngSubmit)="submitForm()">
      <dw-form-item>
        <dw-form-label [dwSm]="6" [dwXs]="24" dwRequired dwFor="email">E-mail</dw-form-label>
        <dw-form-control [dwSm]="14" [dwXs]="24" dwErrorTip="The input is not valid E-mail!">
          <input dw-input formControlName="email" id="email" />
        </dw-form-control>
      </dw-form-item>
      <dw-form-item>
        <dw-form-label [dwSm]="6" [dwXs]="24" dwFor="password" dwRequired>Password</dw-form-label>
        <dw-form-control [dwSm]="14" [dwXs]="24" dwErrorTip="Please input your password!">
          <input dw-input type="password" id="password" formControlName="password" (ngModelChange)="updateConfirmValidator()" />
        </dw-form-control>
      </dw-form-item>
      <dw-form-item>
        <dw-form-label [dwSm]="6" [dwXs]="24" dwFor="checkPassword" dwRequired>Confirm Password</dw-form-label>
        <dw-form-control [dwSm]="14" [dwXs]="24" [dwErrorTip]="errorTpl">
          <input dw-input type="password" formControlName="checkPassword" id="checkPassword" />
          <ng-template #errorTpl let-control>
            <ng-container *ngIf="control.hasError('required')">
              Please confirm your password!
            </ng-container>
            <ng-container *ngIf="control.hasError('confirm')">
              Two passwords that you enter is inconsistent!
            </ng-container>
          </ng-template>
        </dw-form-control>
      </dw-form-item>
      <dw-form-item>
        <dw-form-label [dwSm]="6" [dwXs]="24" dwFor="nickname" dwRequired>
          <span>
            Nickname
            <i dw-icon dw-tooltip dwTooltipTitle="What do you want other to call you" dwType="question-circle" dwTheme="outline"></i>
          </span>
        </dw-form-label>
        <dw-form-control [dwSm]="14" [dwXs]="24" dwErrorTip="Please input your nickname!">
          <input dw-input id="nickname" formControlName="nickname" />
        </dw-form-control>
      </dw-form-item>
      <dw-form-item>
        <dw-form-label [dwSm]="6" [dwXs]="24" dwFor="phoneNumber" dwRequired>Phone Number</dw-form-label>
        <dw-form-control
          [dwSm]="14"
          [dwXs]="24"
          [dwValidateStatus]="validateForm.controls['phoneNumber']"
          dwErrorTip="Please input your phone number!"
        >
          <dw-input-group [dwAddOnBefore]="addOnBeforeTemplate">
            <ng-template #addOnBeforeTemplate>
              <dw-select formControlName="phoneNumberPrefix" class="phone-select">
                <dw-option dwLabel="+86" dwValue="+86"></dw-option>
                <dw-option dwLabel="+87" dwValue="+87"></dw-option>
              </dw-select>
            </ng-template>
            <input formControlName="phoneNumber" id="'phoneNumber'" dw-input />
          </dw-input-group>
        </dw-form-control>
      </dw-form-item>
      <dw-form-item>
        <dw-form-label [dwSm]="6" [dwXs]="24" dwFor="website" dwRequired>Website</dw-form-label>
        <dw-form-control [dwSm]="14" [dwXs]="24" dwErrorTip="Please input website!">
          <input dw-input id="website" formControlName="website" placeholder="website" />
        </dw-form-control>
      </dw-form-item>
      <dw-form-item>
        <dw-form-label [dwSm]="6" [dwXs]="24" dwFor="captcha" dwRequired>Captcha</dw-form-label>
        <dw-form-control
          [dwSm]="14"
          [dwXs]="24"
          dwErrorTip="Please input the captcha you got!"
          dwExtra="We must make sure that your are a human."
        >
          <div dw-row [dwGutter]="8">
            <div dw-col [dwSpan]="12">
              <input dw-input formControlName="captcha" id="captcha" />
            </div>
            <div dw-col [dwSpan]="12">
              <button dw-button (click)="getCaptcha($event)">Get captcha</button>
            </div>
          </div>
        </dw-form-control>
      </dw-form-item>
      <dw-form-item dw-row class="register-area">
        <dw-form-control [dwSpan]="14" [dwOffset]="6">
          <label dw-checkbox formControlName="agree">
            <span>I have read the <a>agreement</a></span>
          </label>
        </dw-form-control>
      </dw-form-item>
      <dw-form-item dw-row class="register-area">
        <dw-form-control [dwSpan]="14" [dwOffset]="6">
          <button dw-button dwType="primary">Register</button>
        </dw-form-control>
      </dw-form-item>
    </form>
  `,

  styles: [
    `
      [dw-form] {
        max-width: 600px;
      }

      .phone-select {
        width: 70px;
      }

      .register-are {
        margin-bottom: 8px;
      }
    `
  ]
})
export class DwDemoFormRegisterComponent implements OnInit {
  validateForm!: FormGroup;

  submitForm(): void {
    for (const i in this.validateForm.controls) {
      this.validateForm.controls[i].markAsDirty();
      this.validateForm.controls[i].updateValueAndValidity();
    }
  }

  updateConfirmValidator(): void {
    /** wait for refresh value */
    Promise.resolve().then(() => this.validateForm.controls.checkPassword.updateValueAndValidity());
  }

  confirmationValidator = (control: FormControl): { [s: string]: boolean } => {
    if (!control.value) {
      return { required: true };
    } else if (control.value !== this.validateForm.controls.password.value) {
      return { confirm: true, error: true };
    }
    return {};
  };

  getCaptcha(e: MouseEvent): void {
    e.preventDefault();
  }

  constructor(private fb: FormBuilder) {}

  ngOnInit(): void {
    this.validateForm = this.fb.group({
      email: [null, [Validators.email, Validators.required]],
      password: [null, [Validators.required]],
      checkPassword: [null, [Validators.required, this.confirmationValidator]],
      nickname: [null, [Validators.required]],
      phoneNumberPrefix: ['+86'],
      phoneNumber: [null, [Validators.required]],
      website: [null, [Validators.required]],
      captcha: [null, [Validators.required]],
      agree: [false]
    });
  }
}
```


---
order: 6
title:
  zh-CN: 时间类控件
  en-US: Time-related Controls
---

## zh-CN

时间类组件的输入和输出类型均为 `Date` 类型，可以通过 [date-fns](https://date-fns.org/) 工具库进行进一步的处理。

## en-US

All the types of input and output in time-related components are `Date`. You can use [date-fns](https://date-fns.org/) to handle it.
```
import { Component, OnInit } from '@angular/core';
import { FormBuilder, FormGroup } from '@angular/forms';

@Component({
  selector: 'dw-demo-form-time-related-controls',
  template: `
    <form dw-form [formGroup]="validateForm" (ngSubmit)="submitForm()">
      <dw-form-item>
        <dw-form-label [dwSm]="8" [dwXs]="24" dwRequired>DatePicker</dw-form-label>
        <dw-form-control [dwSm]="16" [dwXs]="24">
          <dw-date-picker formControlName="datePicker"></dw-date-picker>
        </dw-form-control>
      </dw-form-item>
      <dw-form-item>
        <dw-form-label [dwSm]="8" [dwXs]="24" dwRequired>DatePicker[ShowTime]</dw-form-label>
        <dw-form-control [dwSm]="16" [dwXs]="24">
          <dw-date-picker dwShowTime formControlName="datePickerTime"></dw-date-picker>
        </dw-form-control>
      </dw-form-item>
      <dw-form-item>
        <dw-form-label [dwSm]="8" [dwXs]="24" dwRequired>MonthPicker</dw-form-label>
        <dw-form-control [dwSm]="16" [dwXs]="24">
          <dw-month-picker formControlName="monthPicker"></dw-month-picker>
        </dw-form-control>
      </dw-form-item>
      <dw-form-item>
        <dw-form-label [dwSm]="8" [dwXs]="24" dwRequired>RangePicker</dw-form-label>
        <dw-form-control [dwSm]="16" [dwXs]="24">
          <dw-range-picker formControlName="rangePicker"></dw-range-picker>
        </dw-form-control>
      </dw-form-item>
      <dw-form-item>
        <dw-form-label [dwSm]="8" [dwXs]="24" dwRequired>RangePicker[showTime]</dw-form-label>
        <dw-form-control [dwSm]="16" [dwXs]="24">
          <dw-range-picker dwShowTime formControlName="rangePickerTime"></dw-range-picker>
        </dw-form-control>
      </dw-form-item>
      <dw-form-item>
        <dw-form-label [dwSm]="8" [dwXs]="24" dwRequired>TimePicker</dw-form-label>
        <dw-form-control [dwSm]="16" [dwXs]="24">
          <dw-time-picker formControlName="timePicker"></dw-time-picker>
        </dw-form-control>
      </dw-form-item>
      <dw-form-item>
        <dw-form-control [dwXs]="{ span: 24, offset: 0 }" [dwSm]="{ span: 16, offset: 8 }">
          <button dw-button dwType="primary">Submit</button>
        </dw-form-control>
      </dw-form-item>
    </form>
  `,
  styles: [
    `
      form {
        max-width: 600px;
      }
    `
  ]
})
export class DwDemoFormTimeRelatedControlsComponent implements OnInit {
  validateForm!: FormGroup;

  submitForm(): void {
    console.log(this.validateForm.value);
  }

  constructor(private fb: FormBuilder) {}

  ngOnInit(): void {
    this.validateForm = this.fb.group({
      datePicker: [null],
      datePickerTime: [null],
      monthPicker: [null],
      rangePicker: [[]],
      rangePickerTime: [[]],
      timePicker: [null]
    });
  }
}
```


---
order: 9
title:
  zh-CN: 响应式表单验证
  en-US: Reactive Forms Validation
---

## zh-CN

我们在 `dw-form-control` 上 提供了 `dwValidateStatus` `dwHasFeedback` 等属性，当使用[响应式表单](https://angular.io/guide/reactive-forms#reactive-forms)时，可以自己定义校验的时机和内容。

1. `dwValidateStatus`: 校验状态，默认自动从 `dw-form-control` 中的 `NgControl` 获得校验状态，也可以手动指定为特定的 `NgControl`。
2. `dwHasFeedback`：用于给输入框添加反馈图标。
3. `dwSuccessTip` `dwWarningTip` `dwErrorTip` `dwValidatingTip`：设置不同状态校验文案。
> 当同一种状态下存在多种提示情况时，`dwSuccessTip` `dwWarningTip` `dwErrorTip` `dwValidatingTip` 均支持传入 `TemplateRef<{ $implicit: FormControl }` 类型，可以通过[模板变量]((https://www.angular.cn/guide/template-syntax))导出 `FormControl` 后用于切换不同的提示信息。  
> 当 FormControl.status 为 `INVALID` 并且错误包含 `{warning：true}` 时，`dw-form-control` 显示警告状态。

## en-US

We provide properties like `dwValidateStatus` `dwHasFeedback` in `dw-form-control` to customize your own validate status and message, when using [reactive forms](https://angular.io/guide/reactive-forms#reactive-forms).

1. `dwValidateStatus`: validate status of form components, the default status comes from the `NgControl` in `dw-form-control`, you can set other `NgControl` to it.
2. `dwHasFeedback`: display feed icon of input control
3. `dwSuccessTip` `dwWarningTip` `dwErrorTip` `dwValidatingTip`：display validate message。
> When there are multiple tips in the same state, `dwSuccessTip` `dwWarningTip` `dwErrorTip` `dwValidatingTip` supports the passing `TemplateRef<{ $implicit: FormControl }` type, which can be used to switch tips after exporting `FormControl` via the [template syntax](https://angular.io/guide/template-syntax).  
> When the FormControl.status is `INVALID`, and the errors contains `{warning:true}` , the `dw-form-control` display with warning status.
```
import { Component } from '@angular/core';

import { FormBuilder, FormControl, FormGroup, ValidationErrors, Validators } from '@angular/forms';
import { Observable, Observer } from 'rxjs';

@Component({
  selector: 'dw-demo-form-validate-reactive',
  template: `
    <form dw-form [formGroup]="validateForm" (ngSubmit)="submitForm(validateForm.value)">
      <dw-form-item>
        <dw-form-label [dwSpan]="7" dwRequired>Username</dw-form-label>
        <dw-form-control [dwSpan]="12" dwHasFeedback dwValidatingTip="Validating..." [dwErrorTip]="userErrorTpl">
          <input dw-input formControlName="userName" placeholder="async validate try to write JasonWood" />
          <ng-template #userErrorTpl let-control>
            <ng-container *ngIf="control.hasError('required')">
              Please input your username!
            </ng-container>
            <ng-container *ngIf="control.hasError('duplicated')">
              The username is redundant!
            </ng-container>
          </ng-template>
        </dw-form-control>
      </dw-form-item>
      <dw-form-item>
        <dw-form-label [dwSpan]="7" dwRequired>E-mail</dw-form-label>
        <dw-form-control [dwSpan]="12" dwHasFeedback [dwErrorTip]="emailErrorTpl">
          <input dw-input formControlName="email" placeholder="email" type="email" />
          <ng-template #emailErrorTpl let-control>
            <ng-container *ngIf="control.hasError('email')">
              The input is not valid E-mail!
            </ng-container>
            <ng-container *ngIf="control.hasError('required')">
              Please input your E-mail!
            </ng-container>
          </ng-template>
        </dw-form-control>
      </dw-form-item>
      <dw-form-item>
        <dw-form-label [dwSpan]="7" dwRequired>Password</dw-form-label>
        <dw-form-control [dwSpan]="12" dwHasFeedback dwErrorTip="Please input your password!">
          <input dw-input type="password" formControlName="password" (ngModelChange)="validateConfirmPassword()" />
        </dw-form-control>
      </dw-form-item>
      <dw-form-item>
        <dw-form-label [dwSpan]="7" dwRequired>Confirm Password</dw-form-label>
        <dw-form-control [dwSpan]="12" dwHasFeedback [dwErrorTip]="passwordErrorTpl">
          <input dw-input type="password" formControlName="confirm" placeholder="confirm your password" />
          <ng-template #passwordErrorTpl let-control>
            <ng-container *ngIf="control.hasError('required')">
              Please confirm your password!
            </ng-container>
            <ng-container *ngIf="control.hasError('confirm')">
              Password is inconsistent!
            </ng-container>
          </ng-template>
        </dw-form-control>
      </dw-form-item>
      <dw-form-item>
        <dw-form-label [dwSpan]="7" dwRequired>Comment</dw-form-label>
        <dw-form-control [dwSpan]="12" dwErrorTip="Please write something here!">
          <textarea formControlName="comment" dw-input rows="2" placeholder="write any thing"></textarea>
        </dw-form-control>
      </dw-form-item>
      <dw-form-item>
        <dw-form-control [dwOffset]="7" [dwSpan]="12">
          <button dw-button dwType="primary" [disabled]="!validateForm.valid">Submit</button>
          <button dw-button (click)="resetForm($event)">Reset</button>
        </dw-form-control>
      </dw-form-item>
    </form>
  `,

  styles: [
    `
      [dw-form] {
        max-width: 600px;
      }

      button {
        margin-left: 8px;
      }
    `
  ]
})
export class DwDemoFormValidateReactiveComponent {
  validateForm: FormGroup;

  submitForm(value: { userName: string; email: string; password: string; confirm: string; comment: string }): void {
    for (const key in this.validateForm.controls) {
      this.validateForm.controls[key].markAsDirty();
      this.validateForm.controls[key].updateValueAndValidity();
    }
    console.log(value);
  }

  resetForm(e: MouseEvent): void {
    e.preventDefault();
    this.validateForm.reset();
    for (const key in this.validateForm.controls) {
      this.validateForm.controls[key].markAsPristine();
      this.validateForm.controls[key].updateValueAndValidity();
    }
  }

  validateConfirmPassword(): void {
    setTimeout(() => this.validateForm.controls.confirm.updateValueAndValidity());
  }

  userNameAsyncValidator = (control: FormControl) =>
    new Observable((observer: Observer<ValidationErrors | null>) => {
      setTimeout(() => {
        if (control.value === 'JasonWood') {
          // you have to return `{error: true}` to mark it as an error event
          observer.next({ error: true, duplicated: true });
        } else {
          observer.next(null);
        }
        observer.complete();
      }, 1000);
    });

  confirmValidator = (control: FormControl): { [s: string]: boolean } => {
    if (!control.value) {
      return { error: true, required: true };
    } else if (control.value !== this.validateForm.controls.password.value) {
      return { confirm: true, error: true };
    }
    return {};
  };

  constructor(private fb: FormBuilder) {
    this.validateForm = this.fb.group({
      userName: ['', [Validators.required], [this.userNameAsyncValidator]],
      email: ['', [Validators.email, Validators.required]],
      password: ['', [Validators.required]],
      confirm: ['', [this.confirmValidator]],
      comment: ['', [Validators.required]]
    });
  }
}
```


---
order: 11
title:
  zh-CN: 手动指定表单状态
  en-US: Manual Set Validation Status
---

## zh-CN

用户可以在通过 `dw-form-control` 的 `dwValidateStatus` 属性直接设定表单的状态。

1. `dwValidateStatus`: 校验状态，可选 'success', 'warning', 'error', 'validating'。
2. `dwHasFeedback`：用于给输入框添加反馈图标。
3. `dwSuccessTip` `dwWarningTip` `dwErrorTip` `dwValidatingTip`：设置不同状态校验文案。

## en-US

You can set the form status directly via the `dwValidateStatus` on `dw-form-control`.

1. `dwValidateStatus`: validate status of form components which could be 'success', 'warning', 'error', 'validating'.
2. `dwHasFeedback`: display feed icon of input control
3. `dwSuccessTip` `dwWarningTip` `dwErrorTip` `dwValidatingTip`：display validate message。
```
import { Component } from '@angular/core';

@Component({
  selector: 'dw-demo-form-validate-static',
  template: `
    <form dw-form>
      <dw-form-item>
        <dw-form-label [dwSpan]="5">Fail</dw-form-label>
        <dw-form-control dwValidateStatus="error" [dwSpan]="12" dwErrorTip="Should be combination of numbers & alphabets">
          <input dw-input [ngModel]="'unavailable choice'" name="errorValid" />
        </dw-form-control>
      </dw-form-item>
      <dw-form-item>
        <dw-form-label [dwSpan]="5">Warning</dw-form-label>
        <dw-form-control dwValidateStatus="warning" [dwSpan]="12">
          <input dw-input [ngModel]="'Warning'" name="warningValid" />
        </dw-form-control>
      </dw-form-item>
      <dw-form-item>
        <dw-form-label [dwSpan]="5">Validating</dw-form-label>
        <dw-form-control [dwSpan]="12" dwValidateStatus="validating" dwHasFeedback dwValidatingTip="I'm validating the content">
          <input dw-input [ngModel]="'The content is being validated'" name="validating" />
        </dw-form-control>
      </dw-form-item>
      <dw-form-item>
        <dw-form-label [dwSpan]="5">Success</dw-form-label>
        <dw-form-control [dwSpan]="12" dwValidateStatus="success" dwHasFeedback>
          <input dw-input [ngModel]="'The content'" name="successValid" />
        </dw-form-control>
      </dw-form-item>
      <dw-form-item>
        <dw-form-label [dwSpan]="5">Warning</dw-form-label>
        <dw-form-control [dwSpan]="12" dwValidateStatus="warning" dwHasFeedback dwWarningTip="Should be combination of numbers & alphabets">
          <input dw-input [ngModel]="'Warning'" name="warningHighValid" />
        </dw-form-control>
      </dw-form-item>
      <dw-form-item>
        <dw-form-label [dwSpan]="5">Fail</dw-form-label>
        <dw-form-control [dwSpan]="12" dwValidateStatus="error" dwHasFeedback dwErrorTip="Should be combination of numbers & alphabets">
          <input dw-input [ngModel]="'unavailable choice'" name="invalidValid" />
        </dw-form-control>
      </dw-form-item>
      <dw-form-item>
        <dw-form-label [dwSpan]="5">Success</dw-form-label>
        <dw-form-control [dwSpan]="12" dwValidateStatus="success" dwHasFeedback>
          <dw-date-picker name="date-picker-success"></dw-date-picker>
        </dw-form-control>
      </dw-form-item>
      <dw-form-item>
        <dw-form-label [dwSpan]="5">Warning</dw-form-label>
        <dw-form-control [dwSpan]="12" dwValidateStatus="warning" dwHasFeedback>
          <dw-time-picker name="time-picker-warning"></dw-time-picker>
        </dw-form-control>
      </dw-form-item>
      <dw-form-item>
        <dw-form-label [dwSpan]="5">Error</dw-form-label>
        <dw-form-control [dwSpan]="12" dwValidateStatus="error" dwHasFeedback>
          <dw-select name="select-error" [ngModel]="'Option 1'">
            <dw-option dwValue="Option 1" dwLabel="Option 1"></dw-option>
            <dw-option dwValue="Option 2" dwLabel="Option 2"></dw-option>
          </dw-select>
        </dw-form-control>
      </dw-form-item>
      <dw-form-item>
        <dw-form-label [dwSpan]="5">Validating</dw-form-label>
        <dw-form-control [dwSpan]="12" dwValidateStatus="validating" dwHasFeedback>
          <dw-select name="select-validate" [ngModel]="'Option 2'">
            <dw-option dwValue="Option 1" dwLabel="Option 1"></dw-option>
            <dw-option dwValue="Option 2" dwLabel="Option 2"></dw-option>
          </dw-select>
        </dw-form-control>
      </dw-form-item>
      <dw-form-item>
        <dw-form-label [dwSpan]="5">Success</dw-form-label>
        <dw-form-control [dwSpan]="12" dwValidateStatus="success" dwHasFeedback>
          <dw-input-number name="inputnumber-success" style="width:100%"></dw-input-number>
        </dw-form-control>
      </dw-form-item>
    </form>
  `,
  styles: [
    `
      [dw-form] {
        max-width: 600px;
      }

      dw-date-picker ::ng-deep .ant-calendar-picker {
        width: 100%;
      }

      dw-date-picker,
      dw-time-picker {
        width: 100%;
      }
    `
  ]
})
export class DwDemoFormValidateStaticComponent {}
```


---
order: 10
title:
  zh-CN: 模板驱动表单验证
  en-US: Template-driven Forms Validation
---

## zh-CN

当使用[模板驱动表单](https://angular.io/guide/forms#template-driven-forms)时，模板可以根据模板设定自动进行校验。

1. `dwHasFeedback`：用于给输入框添加反馈图标。
2. `dwSuccessTip` `dwWarningTip` `dwErrorTip` `dwValidatingTip`：设置不同状态校验文案。
> 当同一种状态下存在多种提示情况时，`dwSuccessTip` `dwWarningTip` `dwErrorTip` `dwValidatingTip` 均支持传入 `TemplateRef<{ $implicit: NgModel }` 类型，可以通过[模板变量]((https://www.angular.cn/guide/template-syntax))导出 `NgModel` 后用于切换不同的提示信息。


## en-US

When using [template-driven forms](https://angular.io/guide/forms#template-driven-forms), the form could change its status via the template setting.

1. `dwHasFeedback`: display feed icon of input control
2. `dwSuccessTip` `dwWarningTip` `dwErrorTip` `dwValidatingTip`：display validate message。
> When there are multiple tips in the same state, `dwSuccessTip` `dwWarningTip` `dwErrorTip` `dwValidatingTip` supports the passing `TemplateRef<{ $implicit: NgModel }` type, which can be used to switch tips after exporting `NgModel` via the [template syntax](https://angular.io/guide/template-syntax).
```
import { Component } from '@angular/core';

@Component({
  selector: 'dw-demo-form-validate-template',
  template: `
    <form dw-form>
      <dw-form-item>
        <dw-form-label [dwSpan]="5">Required</dw-form-label>
        <dw-form-control dwHasFeedback [dwSpan]="12" dwErrorTip="Input is required">
          <input dw-input [ngModel]="'Required Input'" name="required" required />
        </dw-form-control>
      </dw-form-item>
      <dw-form-item>
        <dw-form-label [dwSpan]="5">MaxLength</dw-form-label>
        <dw-form-control dwHasFeedback [dwSpan]="12" dwErrorTip="MaxLength is 6">
          <input dw-input [ngModel]="'MaxLength is 6'" name="maxlength" maxlength="6" />
        </dw-form-control>
      </dw-form-item>
      <dw-form-item>
        <dw-form-label [dwSpan]="5">MinLength</dw-form-label>
        <dw-form-control dwHasFeedback [dwSpan]="12" dwErrorTip="MinLength is 6">
          <input dw-input [ngModel]="'MinLength is 6'" name="minlength" minlength="6" />
        </dw-form-control>
      </dw-form-item>
      <dw-form-item>
        <dw-form-label [dwSpan]="5">Email</dw-form-label>
        <dw-form-control dwHasFeedback [dwSpan]="12" dwErrorTip="Email is not valid">
          <input dw-input [ngModel]="'Input Email'" name="email" email />
        </dw-form-control>
      </dw-form-item>
      <dw-form-item>
        <dw-form-label [dwSpan]="5">Pattern</dw-form-label>
        <dw-form-control dwHasFeedback [dwSpan]="12" dwErrorTip="Pattern not match">
          <input dw-input [ngModel]="'Match pattern'" name="pattern" pattern=".{3,}" />
        </dw-form-control>
      </dw-form-item>
      <dw-form-item>
        <dw-form-label [dwSpan]="5">Mix</dw-form-label>
        <dw-form-control dwHasFeedback [dwSpan]="12" [dwErrorTip]="combineTpl">
          <input dw-input [ngModel]="'MaxLength is 12 and MinLength is 6'" name="mix" minlength="6" maxlength="12" required />
          <ng-template #combineTpl let-control>
            <ng-container *ngIf="control.hasError('maxlength')">MaxLength is 12</ng-container>
            <ng-container *ngIf="control.hasError('minlength')">MinLength is 6</ng-container>
            <ng-container *ngIf="control.hasError('required')">Input is required</ng-container>
          </ng-template>
        </dw-form-control>
      </dw-form-item>
    </form>
  `,
  styles: [
    `
      [dw-form] {
        max-width: 600px;
      }
    `
  ]
})
export class DwDemoFormValidateTemplateComponent {}
```
