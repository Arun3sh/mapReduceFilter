# mapReduceFilter

const scores = [
	{
		marks: 32,
		name: 'Yvette Merritt',
	},
	{
		marks: 57,
		name: 'Lillian Ellis',
	},
	{
		marks: 22,
		name: 'Mccall Carter',
	},
	{
		marks: 21,
		name: 'Pate Collier',
	},
	{
		marks: 91,
		name: 'Debra Beard',
	},
	{
		marks: 75,
		name: 'Nettie Hancock',
	},
	{
		marks: 20,
		name: 'Hatfield Hodge',
	},
];

function reducer(previousValue, currentValue) {
	return previousValue + currentValue;
}

let ans = (acc, score) => (acc = acc > score.marks ? acc : score.marks);

// Print the name list - As an array
console.log(scores.map((e) => e.name));

// find those student that passed
console.log(scores.filter((e) => e.marks >= 40));

// Find all the names who failed the exams
console.log(scores.filter((e) => e.marks < 40).map((names) => names.name));

// Find the Average marks
console.log((scores.map((e) => e.marks).reduce(reducer) / scores.length).toFixed(2));

//Find the topper's name
console.log(scores.reduce(ans, 0));
