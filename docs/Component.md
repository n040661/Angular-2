##Component <span style='float:right;font-size:12px;line-height:40px;'>4/16/2017 5:36:18 PM </span>

> **what it does**

Marks a class as an Angular component and collects component configuration
metadata.

> **how to use**

	import { Component } from '@angular/core';
	@Component({
		changeDetection?: ChangeDetectionStrategy,
		viewProviders?: Provider[],
		moduleId?: string,
		templateUrl?: string,
		template?: string,
		styleUrls?: string[],
		styles?: string[],
		animations?: AnimationEntryMetadata[],
		encapsulation?: ViewEncapsulation,
		interpolation?: [string, string],
		entryComponents?: Array<Type<any> | any[]>
	})
	export class MyComponent{
	}

>**description**

A component must belong to an NgModule in order for it to be usable by another component or application. To specify that a component is a member of an NgModule

you should list it in the `declarations` field of that NgModule.

>**metadata properties**

`animations` - list of animations of this component

`changeDetection` - change detection strategy used by this component

`encapsulation` - style encapsulation strategy used by this component

`entryComponents` - list of components that are dynamically inserted into the view of this component

`exportAs` - name under which the component instance is exported in a template

`host` - map of class property to host element bindings for events, properties and attributes

`inputs` - list of class property names to data-bind as component inputs

`interpolation` - custom interpolation markers used in this component's template

Overrides the default encapsulation start and end delimiters (respectively `{{` and `}}`)

![interpolation](../images/interpolation.jpg)

`moduleId` - ES/CommonJS module id of the file in which this component is defined

`outputs` - list of class property names that expose output events that others can subscribe to

`providers` - list of providers available to this component and its children

`queries` -  configure queries that can be injected into the component

`selector` - css selector that identifies this component in a template

`styleUrls` - list of urls to stylesheets to be applied to this component's view

`styles` - inline-defined styles to be applied to this component's view

`template` - inline-defined template for the view

`templateUrl` - url to an external file containing a template for the view

`viewProviders` - list of providers available to this component and its view children