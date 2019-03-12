# DUMBASS Coin

DUMBASS is short for `Decentralized Universal Multifunction Bazinga Artificial Stupid System`. 

We are the world ~~First~~ ~~Greatest~~ Purest AI + Blockchain.

## How DUMBASS works

Our chain is hard forked every time from genesis block.
All things happened in genesis, this made our chain the world fastest safest chain.

## All Code goes here

```python
from numpy import exp, array, random, dot
import hashlib


class Block():
    def __init__(self, input, output):
        genesis_block = str(input) + str(output)
        genesis_block += "ceo_money = 9999999999999999999999999999999999999999"
        self.blockHeight = 0
        self.blockDB = open("blocks", "w")
        self.blockDB.write("======================== " + str(self.blockHeight) + " ========================\n")
        self.blockDB.write(genesis_block)
        self.last_hash = hashlib.sha256(genesis_block).hexdigest()

    def new_block(self, data):
        self.blockHeight += 1
        self.blockDB.write("\n======================== " + str(self.blockHeight) + " ========================\n")
        self.blockDB.write(self.last_hash + "\n")
        self.blockDB.write(data)
        self.last_hash = hashlib.sha256(data).hexdigest()


class NeuralNetwork():
    def __init__(self, block):
        self.block = block
        # Seed the random number generator, so it generates the same numbers
        # every time the program runs.
        random.seed(1)

        # We model a single neuron, with 3 input connections and 1 output connection.
        # We assign random weights to a 3 x 1 matrix, with values in the range -1 to 1
        # and mean 0.
        self.synaptic_weights = 2 * random.random((3, 1)) - 1

    # The Sigmoid function, which describes an S shaped curve.
    # We pass the weighted sum of the inputs through this function to
    # normalise them between 0 and 1.
    def __sigmoid(self, x):
        return 1 / (1 + exp(-x))

    # The derivative of the Sigmoid function.
    # This is the gradient of the Sigmoid curve.
    # It indicates how confident we are about the existing weight.
    def __sigmoid_derivative(self, x):
        return x * (1 - x)

    # We train the neural network through a process of trial and error.
    # Adjusting the synaptic weights each time.
    def train(self, training_set_inputs, training_set_outputs, number_of_training_iterations):
        for iteration in xrange(number_of_training_iterations):
            # Pass the training set through our neural network (a single neuron).
            output = self.think(training_set_inputs)

            # Calculate the error (The difference between the desired output
            # and the predicted output).
            error = training_set_outputs - output

            # Multiply the error by the input and again by the gradient of the Sigmoid curve.
            # This means less confident weights are adjusted more.
            # This means inputs, which are zero, do not cause changes to the weights.
            adjustment = dot(training_set_inputs.T, error * self.__sigmoid_derivative(output))

            # Adjust the weights.
            self.synaptic_weights += adjustment
            # Make Block
            self.block.new_block(str(output) + str(self.synaptic_weights))

    # The neural network thinks.
    def think(self, inputs):
        # Pass inputs through our neural network (our single neuron).
        return self.__sigmoid(dot(inputs, self.synaptic_weights))


if __name__ == "__main__":
    # The training set. We have 4 examples, each consisting of 3 input values
    # and 1 output value.
    training_set_inputs = array([[0, 0, 1], [1, 1, 1], [1, 0, 1], [0, 1, 1]])
    training_set_outputs = array([[0, 1, 1, 0]]).T

    # Initialise blockchain
    blockchain = Block(training_set_inputs, training_set_outputs)

    # Initialise a single neuron neural network.
    neural_network = NeuralNetwork(blockchain)

    print "Random starting synaptic weights: "
    print neural_network.synaptic_weights

    # Train the neural network using a training set.
    # Do it 10,000 times and make small adjustments each time.
    neural_network.train(training_set_inputs, training_set_outputs, 10000)

    print "New synaptic weights after training: "
    print neural_network.synaptic_weights

    # Test the neural network with a new situation.
    print "Considering new situation [1, 0, 0] -> ?: "
    print neural_network.think(array([1, 0, 0]))

```

## Team

- CEO:
    - I'm CEO bitch!
- COO:
    - McDonald Trump
- Programmers:
    - Geoffrey Xinton: did the AI stuff.
    - Satoshi Nakamoto: did the blockchain stuff.
    - Guido van Rossum: for the Python stuff.

## For Angels & VCs & PEs

This project values $1,000,000,000. Send the money first, then I will give you some share.

## Pre sale

You can submit a stupid PR, by adding your account to genesis block. I will judge your stupid PR by your nation and skin color.
The result depends on if I'm happy.

Or, pay me money directly. ~~Of course, I may run away when it makes up 1$~~

[![paypal](https://www.paypalobjects.com/en_US/i/btn/btn_donateCC_LG.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_donations&business=DR5WAL4GT6FV4&item_name=Dev&currency_code=USD&source=url)

## Road Map

- Tomorrow: Add IoT, Drones, and Solar Power.
- Oct 2020: Every animal will have a DUMBASS wallet.
- Mar 2119: Make DUMBASS Interplanetary.
- Aprl 2190: Make cosmos peace.

## How we make money

We will ~~IPO~~, ~~ICO~~, ~~IBO~~, ~~STO~~, ~~IEO~~, ~~make money from you stupid~~.

