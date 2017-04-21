## Render <span style='float:right;font-size:12px;line-height:40px;'>4/21/2017 1:22:30 PM </span>

#### RenderComponentType

	export class RenderComponentType {
	    id: string;
	    templateUrl: string;
	    slotCount: number;
	    encapsulation: ViewEncapsulation;
	    styles: Array<string | any[]>;
	    animations: {
	        [key: string]: Function;
	    };
	    constructor(id: string, templateUrl: string, slotCount: number, encapsulation: ViewEncapsulation, styles: Array<string | any[]>, animations: {
	        [key: string]: Function;
	    });
	}

#### RenderDebugInfo

	export class RenderDebugInfo {
	    injector: Injector;
	    component: any;
	    providerTokens: any[];
	    references: {
	        [key: string]: any;
	    };
	    context: any;
	    source: string;
	}

#### Renderer

- `selectRootElement` (selectorOrNode: string | any, debugInfo?: RenderDebugInfo): any

- `createElement` (parentElement: any, name: string, debugInfo?: RenderDebugInfo): any

- `createViewRoot` (hostElement: any): any

- `createTemplateAnchor` (parentElement: any, debugInfo?: RenderDebugInfo): any

- `createText` (parentElement: any, value: string, debugInfo?: RenderDebugInfo): any

- `projectNodes` (parentElement: any, nodes: any[]): void

- `attachViewAfter` (node: any, viewRootNodes: any[]): void

- `detachView` (viewRootNodes: any[]): void

- `destroyView` (hostElement: any, viewAllNodes: any[]): void

- `listen` (renderElement: any, name: string, callback: Function): Function

- `listenGlobal` (target: string, name: string, callback: Function): Function

- `setElementProperty` (renderElement: any, propertyName: string, propertyValue: any): void

- `setElementAttribute` (renderElement: any, attributeName: string, attributeValue: string): void

- `setBindingDebugInfo` (renderElement: any, propertyName: string, propertyValue: string): void

- `setElementClass` (renderElement: any, className: string, isAdd: boolean): void

- `setElementStyle` (renderElement: any, styleName: string, styleValue: string): void

- `invokeElementMethod` (renderElement: any, methodName: string, args?: any[]): void

- `setText` (renderNode: any, text: string): void

- `animate` (element: any, startingStyles: AnimationStyles, keyframes: AnimationKeyframe[], duration: number, delay: number, easing: string): AnimationPlayer


#### Example

![Renderer](../images/renderer.jpg)

>**RootRenderer**

If you are implementing a custom renderer, you must implement this interface.

The default Renderer implementation is `DomRenderer`. Also available is `WebWorkerRenderer`.

	export declare abstract class RootRenderer {
	    abstract renderComponent(componentType: RenderComponentType): Renderer;
	}