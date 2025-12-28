# Overview

The goal of quantization is shrink the memory used by a model's weights (among other aspects of the model). Quantization can be done by tensor, by channel or by group.

# Quantization per channel
```
def linear_q_symmetric_per_channel(r_tensor, dim, dtype=torch.int8):
    
    output_dim = r_tensor.shape[dim]
    # store the scales
    scale = torch.zeros(output_dim)

    for index in range(output_dim):
        sub_tensor = r_tensor.select(dim, index)
        scale[index] = get_q_scale_symmetric(sub_tensor, dtype=dtype)

    # reshape the scale
    scale_shape = [1] * r_tensor.dim()
    scale_shape[dim] = -1
    scale = scale.view(scale_shape)
    quantized_tensor = linear_q_with_scale_and_zero_point(
        r_tensor, scale=scale, zero_point=0, dtype=dtype)
   
    return quantized_tensor, scale
```

## Notes
- Quantize along either the rows `dim=0` or the columns `dim=1`
- Tends to have a lower quantization error compared to quantizing the entire tensor at once
- Somewhat more complicated compared to tensor quantization 
# Quantization per group

```

```

## Notes
- Group `n` elements elements together, those elements would share the same zero point and scale (quantization parameters)
- Usually grouped in 32, 64, or 128 elements
- Requires more memory:
	- For example, a 4-bit quantization that uses `FP16` for storing the scale will use 4.5 bits, as the scale is $\frac{16}{32}$ or half bit