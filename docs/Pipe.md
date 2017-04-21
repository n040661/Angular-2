## Pipe <span style='float:right;font-size:12px;line-height:40px;'>4/21/2017 1:26:43 PM </span>

>**PipeTransform**

To create a Pipe, you must implement this interface.

#### Syntax

`value | pipeName[:arg0[:arg1...]]`

#### Example

	import {Pipe, PipeTransform} from '@angular/core';
	  @Pipe({name: 'repeat'})
	  export class RepeatPipe implements PipeTransform {
	    transform(value: any, times: number) {
	      return value.repeat(times);
	   }
	 }

Invoking `{{ 'ok' | repeat:3 }}` in a template produces `okokok`.

#### Source code

	export interface PipeTransform {
	    transform(value: any, ...args: any[]): any;
	}