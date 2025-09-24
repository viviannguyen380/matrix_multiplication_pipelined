# matrix_multiplication_pipelined
A pipelined 8X8 matrix multiplier made with Verilog (A*B=C)

Two Read-Only memory modules read in array files, which are passed to four multiply accumulators (MACs) and calculate the result for four terms of the result array 
simultaneously, starting with C11, C12, C21, and C22, in a 2X2 square fashion. 

Once those are calculated, the controller moves indicies to calculate the next 2X2 square of terms directly below the previous. When two columns of the 8X8 multiplier are calculated, the multiplier moves to the next column 2 columns, starting at the first 2 rows. 

When a set of 4 result terms (C terms) is finished being calculated, the four values from the MACs are passed into a buffer, which inserts values one-by one into the result array.
