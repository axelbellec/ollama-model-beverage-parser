# Beverage Parser Model

A specialized fine-tuned Ollama model that extracts structured data from beverage descriptions. This model can identify and parse:

- Beverage types and brands
- Container volumes
- Alcohol content
- Packaging formats

For our beverage parser use case, I chose **llama3.2:1b** as it provides a good balance of efficiency and capability - it can handle the text parsing requirements while being lightweight enough to run efficiently in various environments.

## Installation

Create the model using Ollama:

```bash
$ ollama create "beverage-parser" -f Modelfile
```

## Usage

Run the model with a beverage description:

```bash
$ ollama run beverage-parser "A bottle of Heineken beer, 330ml, 5% alcohol"
{
  "quantity": 1,
  "type": "beer",
  "name": "Heineken",
  "alcohol_percentage": 0.05,
  "volume_ml": 330
}
```

## Example Inputs

### Simple Descriptions

- "A bottle of Heineken beer, 330ml, 5% alcohol"
- "2 cans of Coca-Cola, 355ml each"
- "750ml bottle of Chardonnay wine, 13.5% ABV"

### Complex Descriptions

- "Dom Pérignon Vintage 2010 Champagne (12.5°), 750ml"
- "Six-pack of Sierra Nevada Pale Ale, 12 fl oz bottles, 5.6% alcohol"
- "1.75L Grey Goose vodka, 40% alcohol by volume"

### Non-Alcoholic Beverages

- "A glass of tap water"
- "Monster Energy Drink"
- "3 shots of espresso"

### Alternative Formats

- "75cl Bordeaux red wine, 14 degrees"
- "Handle of Jack Daniel's (1.75L, 80 proof)"
- "500 milliliters of craft IPA at 6.8%"

### Multi-Unit Packages

- "2x 330ml Red Bull sugar free"
- "Magnum of Moët & Chandon (1.5L), 12% ABV"
- "4-pack of 250ml Gin & Tonic cans, 5% alcohol"

## Additional Resources

For more information about Ollama model files:

- [Ollama Modelfile Documentation](https://github.com/ollama/ollama/blob/main/docs/modelfile.md)
