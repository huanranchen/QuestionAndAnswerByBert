# QuestionAndAnswerByBert
a pytorch implement of Hung-Yee Lee's homework.

Thanks for Prof. Lee~ He offer us a excellent and charming maching learning class!


Most of the codes comes from sample code written by TAs.

I modified about 50 lines of code, include:

1. learning rate * 0.5 each epoch

2. doc_stride = 60, max_length = 512

3.In preprocessing, I use random.randint to make the answer position either possible at the beginning of the sequence or the end of the sequence.

4.use Roberta-whole word masking-ext,  MacBert

5.In postprocessing, if start_index > end_index, prob = 0, and find the answer in the original text to prevent special tokens from appearing in the answer

I also tried to use softmax to make the logits become a kind of probability. Documents in Hugging face says that the start_logits is "Span-start scores (before SoftMax)." So I think use softmax can make the result better. But my score decreased about 6%. I don't know why. 

6.Automatic mixed precision

7.Gradient accumulation to make batch_size = 128
