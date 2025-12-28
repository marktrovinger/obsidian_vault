In order to take advantage of the speedups that might occur using torch's implementation of MHA, we need to ensure that the following conditions are true:
- self attention is being computed (i.e., `query`, `key`, and `value` are the same tensor).
- inputs are batched (3D) with `batch_first==True`
- Either autograd is disabled (using `torch.inference_mode` or `torch.no_grad`) or no tensor argument `requires_grad`
- training is disabled (using `.eval()`)
- `add_bias_kv` is `False`
- `add_zero_attn` is `False`
- `batch_first` is `True` and the input is batched
- `kdim` and `vdim` are equal to `embed_dim`
- if a [NestedTensor](https://pytorch.org/docs/stable/nested.html) is passed, neither `key_padding_mask` nor `attn_mask` is passed
- autocast is disabled

Also, thinking about the possible downsides of using this:
- debugging the `torch` code can be kind of annoying, since you have to set a break point within a library