DebugTrace.js
=========

The following are a javascript sample source used DebugTrace.js functions and a log of when the javascript sample was executed.  
Log bodys are automatically indent.

#### Sample source:

	"use strict"

	const debugTrace =  require('./DebugTrace.js/DebugTrace')

	function func1() {
		debugTrace.enter()
		func2()
		func3()
		debugTrace.leave()
	}

	function func2() {
		debugTrace.enter()
		debugTrace.leave()
	}

	function func3() {
		debugTrace.enter()

		const nullValue = null, undefinedValue = undefined
		debugTrace.printValue("nullValue", nullValue)
		debugTrace.printValue("undefinedValue", undefinedValue)

		const boolFalse = false, boolTrue = true
		debugTrace.printValue("boolFalse", boolFalse)
		debugTrace.printValue("boolTrue", boolTrue)

		const number0 = 0, number1_234 = 1.234
		debugTrace.printValue("number0", number0)
		debugTrace.printValue("number1_234", number1_234)

		const stringAAA = "AAA"
		debugTrace.printValue("stringAAA", stringAAA)

		const dateNow = new Date
		debugTrace.printValue("dateNow", dateNow)

		const error = new Error("This is a error.")
		debugTrace.printValue("error", error)

		const array = [1, 2, [1.1, 1.2, 1.3]]
		debugTrace.printValue("array", array)

		const numbers = []
		for (let index = 0; index < 100; ++index) {
			numbers.push(index)
		}
		debugTrace.printValue("numbers", numbers)

		function add(a, b) {
			return a + b
		}
		debugTrace.printValue("add", add)

		const d = (function (a, b) {
			debugTrace.enter()
			const c = a + b
			debugTrace.printValue("c", c)
			debugTrace.leave()
			return c
		})(5, 6)
		debugTrace.printValue("d", d)

		const object = {a:1, b:2, c:3}
		debugTrace.printValue("object", object)

		class Point {
			constructor(x, y) {
				this.x = x
				this.y = y
			}
			add(p) {return new Point(this.x + p.x, this.y + p.y)}
			sub(p) {return new Point(this.x - p.x, this.y - p.y)}
			mul(p) {return new Point(this.x * p.x, this.y * p.y)}
			div(p) {return new Point(this.x / p.x, this.y / p.y)}
		}
		debugTrace.printValue("Point", Point)

		const point1 = new Point(10, 20)
		const point2 = new Point(30, 40)
		const point3 = point1.add(point2).mul(point1.sub(point2))
		debugTrace.printValue("point1", point1)
		debugTrace.printValue("point2", point2)
		debugTrace.printValue("point3", point3)

		debugTrace.leave()
	}

	func1()

#### Log of when the javascript sample has been executed:

	Z:\Develop\JavaScript\DebugTrace.js>node sample
	2016-07-10 08:37:55.197 Z:\Develop\JavaScript\DebugTrace.js\sample.js (func1:6)
	2016-07-10 08:37:55.213 | Z:\Develop\JavaScript\DebugTrace.js\sample.js (func2:13)
	2016-07-10 08:37:55.213 | Z:\Develop\JavaScript\DebugTrace.js\sample.js (func2:14)
	2016-07-10 08:37:55.213 |
	2016-07-10 08:37:55.213 | Z:\Develop\JavaScript\DebugTrace.js\sample.js (func3:18)
	2016-07-10 08:37:55.213 | | nullValue = null (func3:21)
	2016-07-10 08:37:55.213 | | undefinedValue = undefined (func3:22)
	2016-07-10 08:37:55.213 | | boolFalse = false (func3:25)
	2016-07-10 08:37:55.213 | | boolTrue = true (func3:26)
	2016-07-10 08:37:55.229 | | number0 = 0 (func3:29)
	2016-07-10 08:37:55.229 | | number1_234 = 1.234 (func3:30)
	2016-07-10 08:37:55.229 | | stringAAA = "AAA" (func3:33)
	2016-07-10 08:37:55.229 | | dateNow = 2016-07-10 08:37:55.229 (func3:36)
	2016-07-10 08:37:55.229 | | error = Error: This is a error. (func3:39)
	2016-07-10 08:37:55.229 | | array = [1, 2, [1.1, 1.2, 1.3]] (func3:42)
	2016-07-10 08:37:55.245 | | numbers = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15, 16, 17, 18,
	2016-07-10 08:37:55.245 | |   19, 20, 21, 22, 23, 24, 25, 26, 27, 28, 29, 30, 31, 32, 33, 34, 35, 36, 37,
	2016-07-10 08:37:55.245 | |   38, 39, 40, 41, 42, 43, 44, 45, 46, 47, 48, 49, 50, 51, 52, 53, 54, 55, 56,
	2016-07-10 08:37:55.245 | |   57, 58, 59, 60, 61, 62, 63, 64, 65, 66, 67, 68, 69, 70, 71, 72, 73, 74, 75,
	2016-07-10 08:37:55.245 | |   76, 77, 78, 79, 80, 81, 82, 83, 84, 85, 86, 87, 88, 89, 90, 91, 92, 93, 94,
	2016-07-10 08:37:55.245 | |   95, 96, 97, 98, 99
	2016-07-10 08:37:55.245 | | ] (func3:48)
	2016-07-10 08:37:55.245 | | add = function add(a, b) {
	2016-07-10 08:37:55.245 | |         return a + b
	2016-07-10 08:37:55.260 | |     } (func3:53)
	2016-07-10 08:37:55.260 | | Z:\Develop\JavaScript\DebugTrace.js\sample.js (:56)
	2016-07-10 08:37:55.260 | | | c = 11 (:58)
	2016-07-10 08:37:55.260 | | Z:\Develop\JavaScript\DebugTrace.js\sample.js (:59)
	2016-07-10 08:37:55.260 | | d = 11 (func3:62)
	2016-07-10 08:37:55.260 | | object = {
	2016-07-10 08:37:55.260 | |   a:1,
	2016-07-10 08:37:55.260 | |   b:2,
	2016-07-10 08:37:55.260 | |   c:3
	2016-07-10 08:37:55.260 | | } (func3:65)
	2016-07-10 08:37:55.275 | | Point = class Point {
	2016-07-10 08:37:55.275 | |         constructor(x, y) {
	2016-07-10 08:37:55.275 | |             this.x = x
	2016-07-10 08:37:55.275 | |             this.y = y
	2016-07-10 08:37:55.275 | |         }
	2016-07-10 08:37:55.275 | |         add(p) {return new Point(this.x + p.x, this.y + p.y)}
	2016-07-10 08:37:55.275 | |         sub(p) {return new Point(this.x - p.x, this.y - p.y)}
	2016-07-10 08:37:55.275 | |         mul(p) {return new Point(this.x * p.x, this.y * p.y)}
	2016-07-10 08:37:55.275 | |         div(p) {return new Point(this.x / p.x, this.y / p.y)}
	2016-07-10 08:37:55.275 | |     } (func3:77)
	2016-07-10 08:37:55.291 | | point1 = {
	2016-07-10 08:37:55.291 | |   x:10,
	2016-07-10 08:37:55.291 | |   y:20
	2016-07-10 08:37:55.291 | | } (func3:82)
	2016-07-10 08:37:55.291 | | point2 = {
	2016-07-10 08:37:55.291 | |   x:30,
	2016-07-10 08:37:55.291 | |   y:40
	2016-07-10 08:37:55.291 | | } (func3:83)
	2016-07-10 08:37:55.291 | | point3 = {
	2016-07-10 08:37:55.307 | |   x:-800,
	2016-07-10 08:37:55.307 | |   y:-1200
	2016-07-10 08:37:55.307 | | } (func3:84)
	2016-07-10 08:37:55.307 | Z:\Develop\JavaScript\DebugTrace.js\sample.js (func3:86)
	2016-07-10 08:37:55.307 Z:\Develop\JavaScript\DebugTrace.js\sample.js (func1:9)
