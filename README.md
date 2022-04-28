Populate Collectivites Locales
=====

Ceci est un project forker de ma personne, je suis josé Gaydu, developpeur javascript et je vais utilisé cette librairie dans un projet de Collectivites Locales en guadeloupe ma région d'origine.

Je vais modifier cette librairie rapidement.

Nous les avons tous utilisés, des éléments `<select>` qui sont remplis en sélectionnant la valeur d'un autre `<select>`.
Je me suis retrouvé à écrire cette logique encore et encore, alors j'ai décidé de mettre en place ce petit plugin jQuery en tant qu'abstraction.

## Options
Populate accepte deux arguments. Les données réelles qui doivent être injectées dans le DOM et éventuellement un objet avec des options.</p>
<table class="table">
	<thead>
		<tr>
			<th>Proprieté</th>
			<th>Type</th>
			<th>Description</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>exclure</td>
			<td><code>{string}</code></td>
			<td>Le premier nœud qui pourrait servir d'espace réservé.</td>
		</tr>
		<tr>
			<td>select</td>
			<td><code>{string}</code></td>
			<td>Selection d'options.</td>
		</tr>
		<tr>
			<td>onPopulate</td>
			<td><code>{object}</code></td>
			<td>lorem ipsum</td>
		</tr>
	</tbody>
</table>

```js
$('#selector').populate({key:value} , {
    exclude: ':first',
    select: ':eq(2)',
    onPopulate: function (nodes) {}
});
```

## Implementation
Tout d'abord, incluez le plugin en tant que tel :

```html
<script src="jquery-1.9.0.min.js"></script>
<script src="jquery.populate.min.js"></script>
```

Prep your HTML markup:

```html
<select name="categories" id="categories">
	<option value="">Main categories</option>
	<option value="a">Category A</option>
	<option value="b">Category B</option>
	<option value="c">Category C</option>
	<option value="d">Category D</option>
	<option value="e">Category E</option>
</select>
<select disabled="disabled" name="subcategories" id="subcategories">
	<option value="">Select a main category first</option>
</select>
```

Lancez le plugin comme ceci :

```js

// Vous souhaitez probablement encapsuler la logique dans un gestionnaire d'événements
// ou dans un rappel après avoir récupéré les données du serveur
$('#categories').on('change', function () {
    $('#subcategories').populate({key: value});
});
```

Plus d'infos, démos, documentation et tests unitaires sur: http://github.e-sites.nl/populate/
