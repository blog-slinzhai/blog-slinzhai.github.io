---
title: Sort tensor in TensorFlow
date: 2018-12-01 19:29:30
---

# How to sort tensor in TensorFlow

```
import tensorflow as tf

def sortTensor(tensor, ascend=False):
    if ascend==True: tensor = tf.multiply(tensor, -1)
    result = tf.nn.top_k(input=tensor, k=tf.size(tensor))
    values = result.values
    if ascend == True: values = tf.multiply(values, -1)
    indices = result.indices
    return values, indices

cst = tf.constant([12,2,0,1,4,32,67,100,13,-1,54,91,62], dtype=tf.int32)
vls, idxs = sortTensor(cst, True)

with tf.Session(config=tf.ConfigProto(allow_soft_placement=True)) as sess:
    with tf.device("/gpu:0"):
        sess.run([tf.global_variables_initializer(), tf.local_variables_initializer()])
        coord = tf.train.Coordinator()
        threads = tf.train.start_queue_runners(coord=coord)
        print(sess.run(vls))
        print(sess.run(idxs))
        coord.request_stop()
        coord.join(threads)
```
