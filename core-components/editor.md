# Consumer Role

In the GPUFlex network, the consumer is the party that initiates a training job to get a model trained. Consumers can be developers, researchers, or companies who need model training done on distributed GPUs. The platform provides the following capabilities and responsibilities for consumers:

## Define the Training Task

The consumer specifies what they want to accomplish. This includes selecting or providing a model to train (for example, choosing a popular model architecture like ResNet or uploading a custom model script) and indicating the objective (such as classification, regression, etc.). The consumer can also set training hyperparameters or accept recommended defaults. Essentially, the user defines the “experiment” – what model, what data, what settings.

## Dataset Provisioning

&#x20;The consumer provides the dataset on which the model will be trained. GPUFlex supports dataset upload or linking to an existing data source. For instance, a user might upload a CSV of training examples, a folder of images, or a TFRecord/NPZ file, depending on the domain. If the dataset is large, the platform may integrate with decentralized storage (like IPFS or cloud storage) so that workers can fetch pieces of it efficiently. The consumer may also specify data handling instructions (e.g., augmentations, preprocessing steps) if needed. Once uploaded, GPUFlex will handle slicing this dataset for distributed use, but the consumer’s role is to make the data available to the system.

## Model Selection or Initialization

&#x20;Consumers choose how the model should start training. They might select a base model from a library (for example, a pretrained BERT model for NLP fine-tuning) or start from scratch with random initialization. GPUFlex could offer a catalog of common models to pick from, simplifying this step. If the user has custom model code, they could provide a container or environment specification for it. The ability to bring your own model architecture gives consumers flexibility in training arbitrary ML models on the network.

## Cost Estimation and Funding

&#x20;Before the job is executed, the consumer is presented with an estimate of the compute cost. The platform can analyze the job configuration (data size, model complexity, number of rounds/epochs) and estimate how many GPU hours it will require. Based on current network rates, it then quotes a price in GPUX tokens. The consumer needs to fund the job by committing the required amount of GPUX. This is done via a wallet transaction into the GPUFlex smart contract that escrows the payment. The consumer can review the cost and decide to proceed or adjust parameters to fit their budget. Once they confirm, the payment is locked in, ensuring that if the job succeeds, the workers will be paid, and if it fails, the funds can be returned/refunded accordingly.

## Launch and Monitor

&#x20;After funding, the consumer triggers the job start. At this point, the control shifts mostly to the network’s automated processes (dispatcher and workers), but the consumer can still observe what’s happening. GPUFlex provides monitoring tools: the user can see real-time or periodic updates on training progress. This might include metrics like current epoch, training loss/accuracy trends, estimated time to completion, and status of worker nodes (e.g., “8/10 nodes completed round 3”). The interface might show a progress bar or even intermediate results if available. Although the consumer isn’t actively involved in the computation, this transparency builds trust and allows them to intervene (for example, they might have the option to early-stop the job if they see a problem or if the model has converged early).

## Result Retrieval

&#x20;Once the training job is completed and finalized, the consumer receives the outcome. The primary result is the trained model artifacts – typically a file containing the model weights (and architecture, if needed) that can be downloaded. GPUFlex will notify the user that their model is ready. The consumer can download the model through the platform’s UI or API. In addition, the consumer might receive a training report: final metrics (e.g., final accuracy on a validation set if they provided labels for that), logs of the training, and maybe metadata like which nodes participated (for audit purposes). The network ensures that the model delivered is the one resulting from the requested training (integrity verified via internal checks as discussed earlier).

## Feedback and Tuning (Optional)

&#x20;GPUFlex may allow consumers to provide feedback or ratings for the job. For example, after seeing the results, a user could indicate if the outcome met their expectations. This can help the platform improve scheduling or detect issues (if a consumer consistently reports a problem, it might flag certain nodes for inspection). If the model didn’t reach a desired accuracy, the consumer has the option to adjust parameters or provide more data and launch a new round of training (possibly using the just-trained model as the starting point). This iterative experimentation is common in ML development, and GPUFlex’s interface makes it easy to tweak and re-run jobs as needed.



Overall, the consumer’s role is designed to be as simple and high-level as possible: they define what they want, pay for the service, and receive a trained model. GPUFlex abstracts away the complexities of distributed training – the consumer doesn’t have to worry about how many nodes, how to split data, or how to aggregate results. They benefit from the network’s efficiency and robustness while maintaining control over their data and model goals.
