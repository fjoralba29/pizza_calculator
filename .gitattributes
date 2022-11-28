console.clear();

function convertFile(file) {
  const lines = file.split("\n");
  const pizza_eaten = [];

  for (let line of lines) {
    const data = line.split(",");

    const clear_data = {};
    clear_data.name = data[0];
    clear_data.pizza = data[1];
    clear_data.quantity = data[2];

    pizza_eaten.push(clear_data);
  }
  return pizza_eaten;
}

function Calculator(data, ingredients) {
  let total_bianca = 0,
    total_marinara = 0,
    total_margherita = 0;
  let total_wheat = 0,
    total_tomatoes = 0,
    total_cheese = 0;

  for (let item of data) {
    if (item.pizza === "bianca") {
      total_bianca += item.quantity * 52; //1 year has 52 weeks
    } else if (item.pizza === "marinara") {
      total_marinara += item.quantity * 52;
    } else {
      total_margherita += item.quantity * 52;
    }
  }

  for (let type in ingredients) {
    if (type === "bianca") {
      total_wheat += total_bianca * ingredients.bianca.wheat;
    } else if (type === "marinara") {
      total_wheat += total_marinara * ingredients.marinara.wheat;
      total_tomatoes += total_marinara * ingredients.marinara.tomatoes;
    } else {
      total_wheat += total_margherita * ingredients.margherita.wheat;
      total_tomatoes += total_margherita * ingredients.margherita.tomatoes;
      total_cheese += total_margherita * ingredients.margherita.cheese;
    }
  }

  return (
    "Wheat: " +
    total_wheat +
    " gr, Tomatoes: " +
    total_tomatoes +
    " gr, Cheese: " +
    total_cheese +
    " gr"
  );
}

const pizza_eaten_file = `john, margherita, 3 
john,marinara,3
jimmy,margherita,1
alice,marinara,2
bob,bianca,4
luke,bianca,2
tom,margherita,3
daniel,marinara,1
`;

const pizza_ingredients = {
  bianca: { wheat: 150 },
  marinara: { wheat: 100, tomatoes: 100 },
  margherita: { wheat: 120, tomatoes: 80, cheese: 80 }
};

const file_converted = convertFile(pizza_eaten_file.trim());
console.log(Calculator(file_converted, pizza_ingredients));

/*
pizza_ingredients = {
  bianca {wheat: 150}
  marinara {wheat: 100, tomatoes: 100}
  margherita {wheat: 120, tomatoes: 80, cheese: 80 }
}

pizza_eaten = [ {
  name: john, 
  pizza: bianca, 
  num: 3
}
{
  name: jimmi, 
  pizza: marinara, 
  num: 2
}] 
*/
