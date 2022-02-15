# AngularCalculation

# Web Page for Mathematical Calculations using Angular

## AIM:
To design a dynamic website to perform mathematical calculations using Angular Framwork

## DESIGN STEPS:

### Step 1:

Requirement collection.

### Step 2:

Creating the layout using HTML and CSS in component.html file

### Step 3:

Write typescript to perform the calculations.

### Step 4:

Validate the layout in various browsers.

### Step 5:

Validate the HTML code.

### Step 6:

Publish the website in the given URL.

## PROGRAM :
cuboid.component.css
```
* {
    box-sizing: border-box;
    font-family: Arial, Helvetica, sans-serif;
  }
  .container {
    width: 1080px;
    margin-left: auto;
    margin-right: auto;
    padding-top: 30px;
    padding-left: 300px;
    padding-bottom: 500px;
  }
  .content {
    display:block;
    width: 500px;
    background-color:white;
    min-height: 150px;
    font-size: 20px;
  }
  h2{
      text-align: center;
      padding-top: 25px;
  }
  .formelement{
      text-align: center;
      margin-top: 5px;
      margin-bottom: 5px;
  }
```
cuboid.component.html
```
<h2> Volume of cuboid </h2>
    <div class="formelement">
    cLength=<input type="text"[(ngModel)]="clength"> Meters <br/>
    </div>
    <div class="formelement">
    cbreadth=<input type="text"[(ngModel)]="cbreadth"> Meters <br/>
    </div>
    <div class="formelement">
    cheight=<input type="text"[(ngModel)]="cheight"> Meters <br/>
    </div>
    <div class="formelement">
         <input type="button" (click)="onCalculateVolume()" value="calculate Volume"> <br/>
    </div>
    <div class="formelement">
    volume=<input type="text" [value]="volume">Meter<sup>2</sup>
    </div>
```
cuboid.component.ts
```
import { Component } from "@angular/core";


@Component({
    selector:'Cuboid-Volume',
    templateUrl:'./cuboid.component.html',
    styleUrls:['./cuboid.component.css']
})

export class CuboidComponent{
    clength:number;
    cbreadth:number;
    cheight:number;
    volume:number;
    constructor(){
        this.clength = 0;
        this.cbreadth = 0;
        this.cheight = 0;
        this.volume = this.clength*this.cbreadth*this.cheight;
    }
    onCalculateVolume()
    {
        this.volume = this.clength*this.cbreadth*this.cheight;
    }
}
```
rectangle.cpmponent.css
```
* {
    box-sizing: border-box;
    font-family: Arial, Helvetica, sans-serif;
  }
  .container {
    width: 1080px;
    margin-left: auto;
    margin-right: auto;
    padding-top: 30px;
    padding-left: 300px;
    padding-bottom: 500px;
  }
  .content {
    display:block;
    width: 500px;
    background-color:white;
    min-height: 150px;
    font-size: 20px;
  }
  h2{
      text-align: center;
      padding-top: 25px;
  }
  .formelement{
      text-align: center;
      margin-top: 5px;
      margin-bottom: 5px;
  }
```
rectangle.component.html
```
<h2>Area of a Rectangle</h2>
    <div class="formelement">
    Length=<input type="text" [(ngModel)]="length"> Meters <br/>
    </div>
    <div class="formelement">
    Breadth=<input type="text" [(ngModel)]="breadth"> Meters <br/>
    </div>
    <div class="formelement">
        <input type="button" (click)="onCalculate()" value="Calculate Area"> <br/>
    </div>
    <div class="formelement">
    Area=<input type="text" [value]="area"> Meter<sup>2</sup>
    </div>
```
rectangle.component.ts
```
import { Component } from "@angular/core"

@Component({
    selector: 'Rectangle-Area',
    templateUrl:'./rectangle.component.html',
    styleUrls:['./rectangle.component.css']
})
export class RectangleComponent{
    length:number;
    breadth:number;
    area:number;
    constructor(){
        this.length=0;
        this.breadth=0;
        this.area =this.length * this.breadth;

    }
    onCalculate()
    {
        this.area =  this.length * this.breadth;
    }
}
```
app.component.css
```
*{
    box-sizing: border-box;
    font-family: Arial, Helvetica, sans-serif;
    }
    
    body{
    background-color: rgb(226, 164, 207);
    color: black;
    }
    
    .container{
    text-align: center;
    width: 1080px;
    height: 730px;
    margin-left: auto;
    margin-right: auto;
    margin-top: auto;
    }
    
    .content{
    display: block;
    width: 100%;
    margin-left: auto;
    margin-right: auto;
    background-color: rgb(233, 202, 145);
    margin-top: 25px;
    min-height: 275px;
    }
    
    .content1{
    display: block;
    width: 100%;
    margin-left: auto;
    margin-right: auto;
    background-color: rgb(233, 202, 145);
    margin-top: 25px;
    min-height: 300px;
    }
    
    h1{
    color: rgb(0, 0, 0);
    text-align: center;
    padding-top: 20px;
    }
    
    h2{
    color: rgb(0, 0, 0);
    text-align: center;
    padding-top: 20px;
    }
    
    .formelement{
    text-align: center;
    padding-top: 20px;
    font-size: larger;
    }
    
    
    .footer{
    display: inline-block;
    width: 100%;
    height: 35px;
    background-color: darksalmon;
    color: black;
    text-align: center;
    padding-top: 7px;
    font-size: large;
    }
```
app.component.html
```
<body>
    <div class="container">
    <h1>Math Calculations</h1>
    <div class="content">
        <h2><u>Area of Rectangle</u></h2>
        <Rectangle-Area> </Rectangle-Area>
    </div>
    <div class="content1">
        <h2><u>Volume of Cuboid</u></h2>
        <Cuboid-Volume> </Cuboid-Volume>
    </div>
    <div class="footer">
        Developed by Shavedha Y
    </div>
    </div>

</body>
```
app.component.ts
```
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  title = 'mathclaculations--no-strict';
}
```
app.module.ts
```
import { NgModule } from '@angular/core';
import { FormsModule } from '@angular/forms';
import { BrowserModule } from '@angular/platform-browser';

import { AppComponent } from './app.component';
import { CuboidComponent } from './cuboid/cuboid.component';
import { RectangleComponent } from './rectangle/rectangle.component';


@NgModule({
  declarations: [
    AppComponent,RectangleComponent,CuboidComponent
  ],
  imports: [
    BrowserModule,FormsModule
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
```

## OUTPUT:
![output](./befval.png)
![output](./afval.png)



## Result:
Thus we designed the dynamic website to perform mathematical calculations using Angular Framwork.