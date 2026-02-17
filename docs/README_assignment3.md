## Model Checkpoints

This folder contains serialized surrogate model checkpoints saved using Python pickle.

Each `.pkl` file stores:
- Model parameters
- Metadata such as number of qubits, layers, and creation time

### Loading a model

```python
from pathlib import Path
from QuantumModel import QuantumModel  # adjust import if needed

model = QuantumModel.load(Path("models/task2_model_2q.pkl"))
