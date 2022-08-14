# email-signature

Simple email signature block in plain-Jane html, with a little shadow fakery using tables.

If you like it, feel free to use and abuse. If you hate it, that's cool too 🙂

Preview the signature [here](https://bigupjeff.github.io/email-signature/email-signature.html)






Jefferson Real = [
	'Role' 	  => 'Freelance Web Developer'
	'Website' => 'bigupweb.uk'
	'Social'  => [
		'Codepen'
		'Instagram'
		'Facebook'
	]
]


PHP

$Jefferson_Real = [
	'Freelance Web Developer',
	'bigupweb.uk',
	'Follow' => [
		'Codepen',
		'Instagram',
		'Facebook'
	]
]

Jefferson_Real = {
	0:'Freelance Web Developer',
	1:'bigupweb.uk',
	'Follow':{
		0:'Codepen',
		1:'Instagram',
		2:'Facebook'
	}
};

JeffersonReal(
	'Freelance Web Developer',
	'bigupweb.uk',
	Follow = [
		'Codepen',
		'Instagram',
		'Facebook'
	]
){};