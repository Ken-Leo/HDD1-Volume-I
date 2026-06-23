## 附录 A：Q 函数表

$Q(x)$ 函数可以用高斯随机变量的互补累积分布函数来表示，在统计学和工程学中被广泛使用。$Q(x)$ 函数定义为：

$$
Q(x) = \frac{1}{\sqrt{2\pi}} \int_{x}^{\infty} \exp \left\{ -\frac{y^2}{2} \right\} dy \tag{A.1}
$$

该函数计算的是高斯概率密度函数的尾部积分，其中 $\exp[\cdot]$ 为指数函数。通常情况下，对于不同的 $x$ 值，可以通过查询表（Look-up Table）获得 $Q(x)$ 的值。但当 $x \gg 3$ 时，$Q(x)$ 可以近似为：

$$
Q(x) \approx \frac{1}{x\sqrt{2\pi}} \exp \left\{ -\frac{x^2}{2} \right\} \tag{A.2}
$$

下表给出了 $0 \leq x \leq 3.59$ 范围内的 $Q(x)$ 值：

<table><tr><td colspan="1" rowspan="1">x</td><td colspan="1" rowspan="1">Q(x)</td><td colspan="1" rowspan="1">x</td><td colspan="1" rowspan="1">Q(x)</td><td colspan="1" rowspan="1">x</td><td colspan="1" rowspan="1">Q(x)</td><td colspan="1" rowspan="1">x</td><td colspan="1" rowspan="1">Q (x)</td><td colspan="1" rowspan="1">x</td><td colspan="1" rowspan="1">Q(x)</td></tr><tr><td colspan="1" rowspan="1">0</td><td colspan="1" rowspan="1">0.50000</td><td colspan="1" rowspan="1">0.36</td><td colspan="1" rowspan="1">0.35942</td><td colspan="1" rowspan="1">0.72</td><td colspan="1" rowspan="1">0.23576</td><td colspan="1" rowspan="1">1.08</td><td colspan="1" rowspan="1">0.14007</td><td colspan="1" rowspan="1">1.44</td><td colspan="1" rowspan="1">0.0749340</td></tr><tr><td colspan="1" rowspan="1">0.01</td><td colspan="1" rowspan="1">0.49601</td><td colspan="1" rowspan="1">0.37</td><td colspan="1" rowspan="1">0.35569</td><td colspan="1" rowspan="1">0.73</td><td colspan="1" rowspan="1">0.23270</td><td colspan="1" rowspan="1">1.09</td><td colspan="1" rowspan="1">0.13786</td><td colspan="1" rowspan="1">1.45</td><td colspan="1" rowspan="1">0.0735290</td></tr><tr><td colspan="1" rowspan="1">0.02</td><td colspan="1" rowspan="1">0.49202</td><td colspan="1" rowspan="1">0.38</td><td colspan="1" rowspan="1">0.35197</td><td colspan="1" rowspan="1">0.74</td><td colspan="1" rowspan="1">0.22965</td><td colspan="1" rowspan="1">1.10</td><td colspan="1" rowspan="1">0.13567</td><td colspan="1" rowspan="1">1.46</td><td colspan="1" rowspan="1">0.0721450</td></tr><tr><td colspan="1" rowspan="1">0.03</td><td colspan="1" rowspan="1">0.48803</td><td colspan="1" rowspan="1">0.39</td><td colspan="1" rowspan="1">0.34827</td><td colspan="1" rowspan="1">0.75</td><td colspan="1" rowspan="1">0.22663</td><td colspan="1" rowspan="1">1.11</td><td colspan="1" rowspan="1">0.133500</td><td colspan="1" rowspan="1">1.47</td><td colspan="1" rowspan="1">0.070781</td></tr><tr><td colspan="1" rowspan="1">0.04</td><td colspan="1" rowspan="1">0.48405</td><td colspan="1" rowspan="1">0.40</td><td colspan="1" rowspan="1">0.34458</td><td colspan="1" rowspan="1">0.76</td><td colspan="1" rowspan="1">0.22363</td><td colspan="1" rowspan="1">1.12</td><td colspan="1" rowspan="1">0.131360</td><td colspan="1" rowspan="1">1.48</td><td colspan="1" rowspan="1">0.069437</td></tr><tr><td colspan="1" rowspan="1">0.05</td><td colspan="1" rowspan="1">0.48006</td><td colspan="1" rowspan="1">0.41</td><td colspan="1" rowspan="1">0.34090</td><td colspan="1" rowspan="1">0.77</td><td colspan="1" rowspan="1">0.22065</td><td colspan="1" rowspan="1">1.13</td><td colspan="1" rowspan="1">0.129240</td><td colspan="1" rowspan="1">1.49</td><td colspan="1" rowspan="1">0.068112</td></tr><tr><td colspan="1" rowspan="1">0.06</td><td colspan="1" rowspan="1">0.47608</td><td colspan="1" rowspan="1">0.42</td><td colspan="1" rowspan="1">0.33724</td><td colspan="1" rowspan="1">0.78</td><td colspan="1" rowspan="1">0.21770</td><td colspan="1" rowspan="1">1.14</td><td colspan="1" rowspan="1">0.127140</td><td colspan="1" rowspan="1">1.50</td><td colspan="1" rowspan="1">0.066807</td></tr><tr><td colspan="1" rowspan="1">0.07</td><td colspan="1" rowspan="1">0.47210</td><td colspan="1" rowspan="1">0.43</td><td colspan="1" rowspan="1">0.33360</td><td colspan="1" rowspan="1">0.79</td><td colspan="1" rowspan="1">0.21476</td><td colspan="1" rowspan="1">1.15</td><td colspan="1" rowspan="1">0.125070</td><td colspan="1" rowspan="1">1.51</td><td colspan="1" rowspan="1">0.065522</td></tr><tr><td colspan="1" rowspan="1">0.08</td><td colspan="1" rowspan="1">0.46812</td><td colspan="1" rowspan="1">0.44</td><td colspan="1" rowspan="1">0.32997</td><td colspan="1" rowspan="1">0.80</td><td colspan="1" rowspan="1">0.21186</td><td colspan="1" rowspan="1">1.16</td><td colspan="1" rowspan="1">0.123020</td><td colspan="1" rowspan="1">1.52</td><td colspan="1" rowspan="1">0.064255</td></tr><tr><td colspan="1" rowspan="1">0.09</td><td colspan="1" rowspan="1">0.46414</td><td colspan="1" rowspan="1">0.45</td><td colspan="1" rowspan="1">0.32636</td><td colspan="1" rowspan="1">0.81</td><td colspan="1" rowspan="1">0.20897</td><td colspan="1" rowspan="1">1.17</td><td colspan="1" rowspan="1">0.121000</td><td colspan="1" rowspan="1">1.53</td><td colspan="1" rowspan="1">0.063008</td></tr><tr><td colspan="1" rowspan="1">0.10</td><td colspan="1" rowspan="1">0.46017</td><td colspan="1" rowspan="1">0.46</td><td colspan="1" rowspan="1">0.32276</td><td colspan="1" rowspan="1">0.82</td><td colspan="1" rowspan="1">0.20611</td><td colspan="1" rowspan="1">1.18</td><td colspan="1" rowspan="1">0.119000</td><td colspan="1" rowspan="1">1.54</td><td colspan="1" rowspan="1">0.061780</td></tr><tr><td colspan="1" rowspan="1">0.11</td><td colspan="1" rowspan="1">0.45620</td><td colspan="1" rowspan="1">0.47</td><td colspan="1" rowspan="1">0.31918</td><td colspan="1" rowspan="1">0.83</td><td colspan="1" rowspan="1">0.20327</td><td colspan="1" rowspan="1">1.19</td><td colspan="1" rowspan="1">0.117020</td><td colspan="1" rowspan="1">1.55</td><td colspan="1" rowspan="1">0.060571</td></tr><tr><td colspan="1" rowspan="1">0.12</td><td colspan="1" rowspan="1">0.45224</td><td colspan="1" rowspan="1">0.48</td><td colspan="1" rowspan="1">0.31561</td><td colspan="1" rowspan="1">0.84</td><td colspan="1" rowspan="1">0.20045</td><td colspan="1" rowspan="1">1.20</td><td colspan="1" rowspan="1">0.115070</td><td colspan="1" rowspan="1">1.56</td><td colspan="1" rowspan="1">0.059380</td></tr><tr><td colspan="1" rowspan="1">0.13</td><td colspan="1" rowspan="1">0.44828</td><td colspan="1" rowspan="1">0.49</td><td colspan="1" rowspan="1">0.31207</td><td colspan="1" rowspan="1">0.85</td><td colspan="1" rowspan="1">0.19766</td><td colspan="1" rowspan="1">1.21</td><td colspan="1" rowspan="1">0.113140</td><td colspan="1" rowspan="1">1.57</td><td colspan="1" rowspan="1">0.058208</td></tr><tr><td colspan="1" rowspan="1">0.14</td><td colspan="1" rowspan="1">0.44433</td><td colspan="1" rowspan="1">0.50</td><td colspan="1" rowspan="1">0.30854</td><td colspan="1" rowspan="1">0.86</td><td colspan="1" rowspan="1">0.19489</td><td colspan="1" rowspan="1">1.22</td><td colspan="1" rowspan="1">0.111230</td><td colspan="1" rowspan="1">1.58</td><td colspan="1" rowspan="1">0.057053</td></tr><tr><td colspan="1" rowspan="1">0.15</td><td colspan="1" rowspan="1">0.44038</td><td colspan="1" rowspan="1">0.51</td><td colspan="1" rowspan="1">0.30503</td><td colspan="1" rowspan="1">0.87</td><td colspan="1" rowspan="1">0.19215</td><td colspan="1" rowspan="1">1.23</td><td colspan="1" rowspan="1">0.109350</td><td colspan="1" rowspan="1">1.59</td><td colspan="1" rowspan="1">0.055917</td></tr><tr><td colspan="1" rowspan="1">0.16</td><td colspan="1" rowspan="1">0.43644</td><td colspan="1" rowspan="1">0.52</td><td colspan="1" rowspan="1">0.30153</td><td colspan="1" rowspan="1">0.88</td><td colspan="1" rowspan="1">0.18943</td><td colspan="1" rowspan="1">1.24</td><td colspan="1" rowspan="1">0.107490</td><td colspan="1" rowspan="1">1.60</td><td colspan="1" rowspan="1">0.054799</td></tr><tr><td colspan="1" rowspan="1">0.17</td><td colspan="1" rowspan="1">0.43251</td><td colspan="1" rowspan="1">0.53</td><td colspan="1" rowspan="1">0.29806</td><td colspan="1" rowspan="1">0.89</td><td colspan="1" rowspan="1">0.18673</td><td colspan="1" rowspan="1">1.25</td><td colspan="1" rowspan="1">0.105650</td><td colspan="1" rowspan="1">1.61</td><td colspan="1" rowspan="1">0.053699</td></tr><tr><td colspan="1" rowspan="1">0.18</td><td colspan="1" rowspan="1">0.42858</td><td colspan="1" rowspan="1">0.54</td><td colspan="1" rowspan="1">0.29460</td><td colspan="1" rowspan="1">0.90</td><td colspan="1" rowspan="1">0.18406</td><td colspan="1" rowspan="1">1.26</td><td colspan="1" rowspan="1">0.103830</td><td colspan="1" rowspan="1">1.62</td><td colspan="1" rowspan="1">0.052616</td></tr><tr><td colspan="1" rowspan="1">0.19</td><td colspan="1" rowspan="1">0.42465</td><td colspan="1" rowspan="1">0.55</td><td colspan="1" rowspan="1">0.29116</td><td colspan="1" rowspan="1">0.91</td><td colspan="1" rowspan="1">0.18141</td><td colspan="1" rowspan="1">1.27</td><td colspan="1" rowspan="1">0.102040</td><td colspan="1" rowspan="1">1.63</td><td colspan="1" rowspan="1">0.051551</td></tr><tr><td colspan="1" rowspan="1">0.20</td><td colspan="1" rowspan="1">0.42074</td><td colspan="1" rowspan="1">0.56</td><td colspan="1" rowspan="1">0.28774</td><td colspan="1" rowspan="1">0.92</td><td colspan="1" rowspan="1">0.17879</td><td colspan="1" rowspan="1">1.28</td><td colspan="1" rowspan="1">0.100270</td><td colspan="1" rowspan="1">1.64</td><td colspan="1" rowspan="1">0.050503</td></tr><tr><td colspan="1" rowspan="1">0.21</td><td colspan="1" rowspan="1">0.41683</td><td colspan="1" rowspan="1">0.57</td><td colspan="1" rowspan="1">0.28434</td><td colspan="1" rowspan="1">0.93</td><td colspan="1" rowspan="1">0.17619</td><td colspan="1" rowspan="1">1.29</td><td colspan="1" rowspan="1">0.098525</td><td colspan="1" rowspan="1">1.65</td><td colspan="1" rowspan="1">0.049471</td></tr><tr><td colspan="1" rowspan="1">0.22</td><td colspan="1" rowspan="1">0.41294</td><td colspan="1" rowspan="1">0.58</td><td colspan="1" rowspan="1">0.28096</td><td colspan="1" rowspan="1">0.94</td><td colspan="1" rowspan="1">0.17361</td><td colspan="1" rowspan="1">1.30</td><td colspan="1" rowspan="1">0.096800</td><td colspan="1" rowspan="1">1.66</td><td colspan="1" rowspan="1">0.048457</td></tr><tr><td colspan="1" rowspan="1">0.23</td><td colspan="1" rowspan="1">0.40905</td><td colspan="1" rowspan="1">0.59</td><td colspan="1" rowspan="1">0.27760</td><td colspan="1" rowspan="1">0.95</td><td colspan="1" rowspan="1">0.17106</td><td colspan="1" rowspan="1">1.31</td><td colspan="1" rowspan="1">0.095098</td><td colspan="1" rowspan="1">1.67</td><td colspan="1" rowspan="1">0.047460</td></tr><tr><td colspan="1" rowspan="1">0.24</td><td colspan="1" rowspan="1">0.40517</td><td colspan="1" rowspan="1">0.60</td><td colspan="1" rowspan="1">0.27425</td><td colspan="1" rowspan="1">0.96</td><td colspan="1" rowspan="1">0.16853</td><td colspan="1" rowspan="1">1.32</td><td colspan="1" rowspan="1">0.093418</td><td colspan="1" rowspan="1">1.68</td><td colspan="1" rowspan="1">0.046479</td></tr><tr><td colspan="1" rowspan="1">0.25</td><td colspan="1" rowspan="1">0.40129</td><td colspan="1" rowspan="1">0.61</td><td colspan="1" rowspan="1">0.27093</td><td colspan="1" rowspan="1">0.97</td><td colspan="1" rowspan="1">0.16602</td><td colspan="1" rowspan="1">1.33</td><td colspan="1" rowspan="1">0.091759</td><td colspan="1" rowspan="1">1.69</td><td colspan="1" rowspan="1">0.045514</td></tr><tr><td colspan="1" rowspan="1">0.26</td><td colspan="1" rowspan="1">0.39743</td><td colspan="1" rowspan="1">0.62</td><td colspan="1" rowspan="1">0.26763</td><td colspan="1" rowspan="1">0.98</td><td colspan="1" rowspan="1">0.16354</td><td colspan="1" rowspan="1">1.34</td><td colspan="1" rowspan="1">0.090123</td><td colspan="1" rowspan="1">1.70</td><td colspan="1" rowspan="1">0.044565</td></tr><tr><td colspan="1" rowspan="1">0.27</td><td colspan="1" rowspan="1">0.39358</td><td colspan="1" rowspan="1">0.63</td><td colspan="1" rowspan="1">0.26435</td><td colspan="1" rowspan="1">0.99</td><td colspan="1" rowspan="1">0.16109</td><td colspan="1" rowspan="1">1.35</td><td colspan="1" rowspan="1">0.088508</td><td colspan="1" rowspan="1">1.71</td><td colspan="1" rowspan="1">0.043633</td></tr><tr><td colspan="1" rowspan="1">0.28</td><td colspan="1" rowspan="1">0.38974</td><td colspan="1" rowspan="1">0.64</td><td colspan="1" rowspan="1">0.26109</td><td colspan="1" rowspan="1">1.00</td><td colspan="1" rowspan="1">0.15866</td><td colspan="1" rowspan="1">1.36</td><td colspan="1" rowspan="1">0.086915</td><td colspan="1" rowspan="1">1.72</td><td colspan="1" rowspan="1">0.042716</td></tr><tr><td colspan="1" rowspan="1">0.29</td><td colspan="1" rowspan="1">0.38591</td><td colspan="1" rowspan="1">0.65</td><td colspan="1" rowspan="1">0.25785</td><td colspan="1" rowspan="1">1.01</td><td colspan="1" rowspan="1">0.15625</td><td colspan="1" rowspan="1">1.37</td><td colspan="1" rowspan="1">0.085343</td><td colspan="1" rowspan="1">1.73</td><td colspan="1" rowspan="1">0.041815</td></tr><tr><td colspan="1" rowspan="1">0.30</td><td colspan="1" rowspan="1">0.38209</td><td colspan="1" rowspan="1">0.66</td><td colspan="1" rowspan="1">0.25463</td><td colspan="1" rowspan="1">1.02</td><td colspan="1" rowspan="1">0.15386</td><td colspan="1" rowspan="1">1.38</td><td colspan="1" rowspan="1">0.083793</td><td colspan="1" rowspan="1">1.74</td><td colspan="1" rowspan="1">0.040930</td></tr><tr><td colspan="1" rowspan="1">0.31</td><td colspan="1" rowspan="1">0.37828</td><td colspan="1" rowspan="1">0.67</td><td colspan="1" rowspan="1">0.25143</td><td colspan="1" rowspan="1">1.03</td><td colspan="1" rowspan="1">0.15151</td><td colspan="1" rowspan="1">1.39</td><td colspan="1" rowspan="1">0.082264</td><td colspan="1" rowspan="1">1.75</td><td colspan="1" rowspan="1">0.040059</td></tr><tr><td colspan="1" rowspan="1">0.32</td><td colspan="1" rowspan="1">0.37448</td><td colspan="1" rowspan="1">0.68</td><td colspan="1" rowspan="1">0.24825</td><td colspan="1" rowspan="1">1.04</td><td colspan="1" rowspan="1">0.14917</td><td colspan="1" rowspan="1">1.40</td><td colspan="1" rowspan="1">0.080757</td><td colspan="1" rowspan="1">1.76</td><td colspan="1" rowspan="1">0.039204</td></tr><tr><td colspan="1" rowspan="1">0.33</td><td colspan="1" rowspan="1">0.37070</td><td colspan="1" rowspan="1">0.69</td><td colspan="1" rowspan="1">0.24510</td><td colspan="1" rowspan="1">1.05</td><td colspan="1" rowspan="1">0.14686</td><td colspan="1" rowspan="1">1.41</td><td colspan="1" rowspan="1">0.079270</td><td colspan="1" rowspan="1">1.77</td><td colspan="1" rowspan="1">0.038364</td></tr><tr><td colspan="1" rowspan="1">0.34</td><td colspan="1" rowspan="1">0.36693</td><td colspan="1" rowspan="1">0.70</td><td colspan="1" rowspan="1">0.24196</td><td colspan="1" rowspan="1">1.06</td><td colspan="1" rowspan="1">0.14457</td><td colspan="1" rowspan="1">1.42</td><td colspan="1" rowspan="1">0.077804</td><td colspan="1" rowspan="1">1.78</td><td colspan="1" rowspan="1">0.037538</td></tr><tr><td colspan="1" rowspan="1">0.35</td><td colspan="1" rowspan="1">0.36317</td><td colspan="1" rowspan="1">0.71</td><td colspan="1" rowspan="1">0.23885</td><td colspan="1" rowspan="1">1.07</td><td colspan="1" rowspan="1">0.14231</td><td colspan="1" rowspan="1">1.43</td><td colspan="1" rowspan="1">0.076359</td><td colspan="1" rowspan="1">1.79</td><td colspan="1" rowspan="1">0.036727</td></tr><tr><td colspan="1" rowspan="1">1.80</td><td colspan="1" rowspan="1">0.035930</td><td colspan="1" rowspan="1">2.16</td><td colspan="1" rowspan="1">0.0153860</td><td colspan="1" rowspan="1">2.52</td><td colspan="1" rowspan="1">0.0058677</td><td colspan="1" rowspan="1">2.88</td><td colspan="1" rowspan="1">0.00198840</td><td colspan="1" rowspan="1">3.24</td><td colspan="1" rowspan="1">0.00059765</td></tr><tr><td colspan="1" rowspan="1">1.81</td><td colspan="1" rowspan="1">0.035148</td><td colspan="1" rowspan="1">2.17</td><td colspan="1" rowspan="1">0.0150030</td><td colspan="1" rowspan="1">2.53</td><td colspan="1" rowspan="1">0.0057031</td><td colspan="1" rowspan="1">2.89</td><td colspan="1" rowspan="1">0.00192620</td><td colspan="1" rowspan="1">3.25</td><td colspan="1" rowspan="1">0.00057703</td></tr><tr><td colspan="1" rowspan="1">1.82</td><td colspan="1" rowspan="1">0.034380</td><td colspan="1" rowspan="1">2.18</td><td colspan="1" rowspan="1">0.0146290</td><td colspan="1" rowspan="1">2.54</td><td colspan="1" rowspan="1">0.0055426</td><td colspan="1" rowspan="1">2.90</td><td colspan="1" rowspan="1">0.00186580</td><td colspan="1" rowspan="1">3.26</td><td colspan="1" rowspan="2">0.000557060.00053774</td></tr><tr><td colspan="1" rowspan="1">1.83</td><td colspan="1" rowspan="1">0.033625</td><td colspan="1" rowspan="1">2.19</td><td colspan="1" rowspan="1">0.0142620</td><td colspan="1" rowspan="1">2.55</td><td colspan="1" rowspan="1">0.0053861</td><td colspan="1" rowspan="1">2.91</td><td colspan="1" rowspan="1">0.00180710</td><td colspan="1" rowspan="1">3.27</td></tr><tr><td colspan="1" rowspan="1">1.84</td><td colspan="1" rowspan="1">0.032884</td><td colspan="1" rowspan="1">2.20</td><td colspan="1" rowspan="1">0.0139030</td><td colspan="1" rowspan="1">2.56</td><td colspan="1" rowspan="1">0.0052336</td><td colspan="1" rowspan="1">2.92</td><td colspan="1" rowspan="1">0.00175020</td><td colspan="1" rowspan="1">3.28</td><td colspan="1" rowspan="1">0.00051904</td></tr><tr><td colspan="1" rowspan="1">1.85</td><td colspan="1" rowspan="1">0.032157</td><td colspan="1" rowspan="1">2.21</td><td colspan="1" rowspan="1">0.0135530</td><td colspan="1" rowspan="1">2.57</td><td colspan="1" rowspan="1">0.0050849</td><td colspan="1" rowspan="1">2.93</td><td colspan="1" rowspan="1">0.00169480</td><td colspan="1" rowspan="2">3.293.30</td><td colspan="1" rowspan="2">0.000500940.00048342</td></tr><tr><td colspan="1" rowspan="1">1.86</td><td colspan="1" rowspan="1">0.031443</td><td colspan="1" rowspan="1">2.22</td><td colspan="1" rowspan="1">0.0132090</td><td colspan="1" rowspan="1">2.58</td><td colspan="1" rowspan="1">0.0049400</td><td colspan="1" rowspan="1">2.94</td><td colspan="1" rowspan="1">0.00164110</td></tr><tr><td colspan="1" rowspan="1">1.87</td><td colspan="1" rowspan="1">0.030742</td><td colspan="1" rowspan="1">2.23</td><td colspan="1" rowspan="1">0.0128740</td><td colspan="1" rowspan="1">2.59</td><td colspan="1" rowspan="1">0.0047988</td><td colspan="1" rowspan="1">2.95</td><td colspan="1" rowspan="1">0.00158890</td><td colspan="1" rowspan="1">3.31</td><td colspan="1" rowspan="2">0.000466480.00045009</td></tr><tr><td colspan="1" rowspan="1">1.88</td><td colspan="1" rowspan="1">0.030054</td><td colspan="1" rowspan="1">2.24</td><td colspan="1" rowspan="1">0.0125450</td><td colspan="1" rowspan="1">2.60</td><td colspan="1" rowspan="1">0.0046612</td><td colspan="1" rowspan="1">2.96</td><td colspan="1" rowspan="1">0.00153820</td><td colspan="1" rowspan="1">3.32</td></tr><tr><td colspan="1" rowspan="1">1.89</td><td colspan="1" rowspan="1">0.029379</td><td colspan="1" rowspan="1">2.25</td><td colspan="1" rowspan="1">0.0122240</td><td colspan="1" rowspan="1">2.61</td><td colspan="1" rowspan="1">0.0045271</td><td colspan="1" rowspan="1">2.97</td><td colspan="1" rowspan="1">0.00148900</td><td colspan="1" rowspan="1">3.33</td><td colspan="1" rowspan="1">0.00043423</td></tr><tr><td colspan="1" rowspan="1">1.90</td><td colspan="1" rowspan="1">0.028717</td><td colspan="1" rowspan="1">2.26</td><td colspan="1" rowspan="1">0.0119110</td><td colspan="1" rowspan="1">2.62</td><td colspan="1" rowspan="1">0.0043965</td><td colspan="1" rowspan="1">2.98</td><td colspan="1" rowspan="1">0.00144120</td><td colspan="1" rowspan="1">3.34</td><td colspan="1" rowspan="1">0.00041889</td></tr><tr><td colspan="1" rowspan="1">1.91</td><td colspan="1" rowspan="1">0.028067</td><td colspan="1" rowspan="1">2.27</td><td colspan="1" rowspan="1">0.0116040</td><td colspan="1" rowspan="1">2.63</td><td colspan="1" rowspan="1">0.0042692</td><td colspan="1" rowspan="1">2.99</td><td colspan="1" rowspan="1">0.00139490</td><td colspan="1" rowspan="1">3.35</td><td colspan="1" rowspan="1">0.00040406</td></tr><tr><td colspan="1" rowspan="1">1.92</td><td colspan="1" rowspan="1">0.027429</td><td colspan="1" rowspan="1">2.28</td><td colspan="1" rowspan="1">0.0113040</td><td colspan="1" rowspan="1">2.64</td><td colspan="1" rowspan="1">0.0041453</td><td colspan="1" rowspan="1">3.00</td><td colspan="1" rowspan="1">0.00134990</td><td colspan="1" rowspan="1">3.36</td><td colspan="1" rowspan="1">0.00038971</td></tr><tr><td colspan="1" rowspan="1">1.93</td><td colspan="1" rowspan="1">0.026803</td><td colspan="1" rowspan="1">2.29</td><td colspan="1" rowspan="1">0.0110110</td><td colspan="1" rowspan="1">2.65</td><td colspan="1" rowspan="1">0.0040246</td><td colspan="1" rowspan="1">3.01</td><td colspan="1" rowspan="1">0.00130620</td><td colspan="1" rowspan="1">3.37</td><td colspan="1" rowspan="1">0.00037584</td></tr><tr><td colspan="1" rowspan="1">1.94</td><td colspan="1" rowspan="1">0.026190</td><td colspan="1" rowspan="1">2.30</td><td colspan="1" rowspan="1">0.0107240</td><td colspan="1" rowspan="1">2.66</td><td colspan="1" rowspan="1">0.0039070</td><td colspan="1" rowspan="1">3.02</td><td colspan="1" rowspan="1">0.00126390</td><td colspan="1" rowspan="1">3.38</td><td colspan="1" rowspan="1">0.00036243</td></tr><tr><td colspan="1" rowspan="1">1.95</td><td colspan="1" rowspan="1">0.025588</td><td colspan="1" rowspan="1">2.31</td><td colspan="1" rowspan="1">0.0104440</td><td colspan="1" rowspan="1">2.67</td><td colspan="1" rowspan="1">0.0037926</td><td colspan="1" rowspan="1">3.03</td><td colspan="1" rowspan="1">0.00122280</td><td colspan="1" rowspan="1">3.39</td><td colspan="1" rowspan="1">0.00034946</td></tr><tr><td colspan="1" rowspan="1">1.96</td><td colspan="1" rowspan="1">0.024998</td><td colspan="1" rowspan="1">2.32</td><td colspan="1" rowspan="1">0.0101700</td><td colspan="1" rowspan="1">2.68</td><td colspan="1" rowspan="1">0.0036811</td><td colspan="1" rowspan="1">3.04</td><td colspan="1" rowspan="1">0.00118290</td><td colspan="1" rowspan="1">3.40</td><td colspan="1" rowspan="1">0.00033693</td></tr><tr><td colspan="1" rowspan="1">1.97</td><td colspan="1" rowspan="1">0.024419</td><td colspan="1" rowspan="1">2.33</td><td colspan="1" rowspan="1">0.0099031</td><td colspan="1" rowspan="1">2.69</td><td colspan="1" rowspan="1">0.0035726</td><td colspan="1" rowspan="1">3.05</td><td colspan="1" rowspan="1">0.00114420</td><td colspan="1" rowspan="1">3.41</td><td colspan="1" rowspan="1">0.00032481</td></tr><tr><td colspan="1" rowspan="1">1.98</td><td colspan="1" rowspan="1">0.023852</td><td colspan="1" rowspan="1">2.34</td><td colspan="1" rowspan="1">0.0096419</td><td colspan="1" rowspan="1">2.70</td><td colspan="1" rowspan="1">0.0034670</td><td colspan="1" rowspan="1">3.06</td><td colspan="1" rowspan="1">0.00110670</td><td colspan="1" rowspan="1">3.42</td><td colspan="1" rowspan="1">0.00031311</td></tr><tr><td colspan="1" rowspan="1">1.99</td><td colspan="1" rowspan="1">0.023295</td><td colspan="1" rowspan="1">2.35</td><td colspan="1" rowspan="1">0.0093867</td><td colspan="1" rowspan="1">2.71</td><td colspan="1" rowspan="1">0.0033642</td><td colspan="1" rowspan="1">3.07</td><td colspan="1" rowspan="1">0.00107030</td><td colspan="1" rowspan="1">3.43</td><td colspan="1" rowspan="1">0.00030179</td></tr><tr><td colspan="1" rowspan="1">2.00</td><td colspan="1" rowspan="1">0.022750</td><td colspan="1" rowspan="1">2.36</td><td colspan="1" rowspan="1">0.0091375</td><td colspan="1" rowspan="1">2.72</td><td colspan="1" rowspan="1">0.0032641</td><td colspan="1" rowspan="1">3.08</td><td colspan="1" rowspan="1">0.00103500</td><td colspan="1" rowspan="1">3.44</td><td colspan="1" rowspan="1">0.00029086</td></tr><tr><td colspan="1" rowspan="1">2.01</td><td colspan="1" rowspan="1">0.022216</td><td colspan="1" rowspan="1">2.37</td><td colspan="1" rowspan="1">0.0088940</td><td colspan="1" rowspan="1">2.73</td><td colspan="1" rowspan="1">0.0031667</td><td colspan="1" rowspan="1">3.09</td><td colspan="1" rowspan="1">0.00100080</td><td colspan="1" rowspan="1">3.45</td><td colspan="1" rowspan="1">0.00028029</td></tr><tr><td colspan="1" rowspan="1">2.02</td><td colspan="1" rowspan="1">0.021692</td><td colspan="1" rowspan="1">2.38</td><td colspan="1" rowspan="1">0.0086563</td><td colspan="1" rowspan="1">2.74</td><td colspan="1" rowspan="1">0.0030720</td><td colspan="1" rowspan="1">3.10</td><td colspan="1" rowspan="1">0.00096760</td><td colspan="1" rowspan="1">3.46</td><td colspan="1" rowspan="1">0.00027009</td></tr><tr><td colspan="1" rowspan="1">2.03</td><td colspan="1" rowspan="1">0.021178</td><td colspan="1" rowspan="1">2.39</td><td colspan="1" rowspan="1">0.0084242</td><td colspan="1" rowspan="1">2.75</td><td colspan="1" rowspan="1">0.0029798</td><td colspan="1" rowspan="1">3.11</td><td colspan="1" rowspan="1">0.00093544</td><td colspan="1" rowspan="1">3.47</td><td colspan="1" rowspan="1">0.00026023</td></tr><tr><td colspan="1" rowspan="1">2.04</td><td colspan="1" rowspan="1">0.020675</td><td colspan="1" rowspan="1">2.40</td><td colspan="1" rowspan="1">0.0081975</td><td colspan="1" rowspan="1">2.76</td><td colspan="1" rowspan="1">0.0028901</td><td colspan="1" rowspan="1">3.12</td><td colspan="1" rowspan="1">0.00090426</td><td colspan="1" rowspan="1">3.48</td><td colspan="1" rowspan="1">0.00025071</td></tr><tr><td colspan="1" rowspan="1">2.05</td><td colspan="1" rowspan="1">0.020182</td><td colspan="1" rowspan="1">2.41</td><td colspan="1" rowspan="1">0.0079763</td><td colspan="1" rowspan="1">2.77</td><td colspan="1" rowspan="1">0.0028028</td><td colspan="1" rowspan="1">3.13</td><td colspan="1" rowspan="1">0.00087403</td><td colspan="1" rowspan="1">3.49</td><td colspan="1" rowspan="1">0.00024151</td></tr><tr><td colspan="1" rowspan="1">2.06</td><td colspan="1" rowspan="1">0.019699</td><td colspan="1" rowspan="1">2.42</td><td colspan="1" rowspan="1">0.0077603</td><td colspan="1" rowspan="1">2.78</td><td colspan="1" rowspan="1">0.0027179</td><td colspan="1" rowspan="1">3.14</td><td colspan="1" rowspan="1">0.00084474</td><td colspan="1" rowspan="1">3.50</td><td colspan="1" rowspan="1">0.00023263</td></tr><tr><td colspan="1" rowspan="1">2.07</td><td colspan="1" rowspan="1">0.019226</td><td colspan="1" rowspan="1">2.43</td><td colspan="1" rowspan="1">0.0075494</td><td colspan="1" rowspan="1">2.79</td><td colspan="1" rowspan="1">0.0026354</td><td colspan="1" rowspan="1">3.15</td><td colspan="1" rowspan="1">0.00081635</td><td colspan="1" rowspan="1">3.51</td><td colspan="1" rowspan="1">0.00022405</td></tr><tr><td colspan="1" rowspan="1">2.08</td><td colspan="1" rowspan="1">0.018763</td><td colspan="1" rowspan="1">2.44</td><td colspan="1" rowspan="1">0.0073436</td><td colspan="1" rowspan="1">2.80</td><td colspan="1" rowspan="1">0.0025551</td><td colspan="1" rowspan="1">3.16</td><td colspan="1" rowspan="1">0.00078885</td><td colspan="1" rowspan="1">3.52</td><td colspan="1" rowspan="1">0.00021577</td></tr><tr><td colspan="1" rowspan="1">2.09</td><td colspan="1" rowspan="1">0.018309</td><td colspan="1" rowspan="1">2.45</td><td colspan="1" rowspan="1">0.0071428</td><td colspan="1" rowspan="1">2.81</td><td colspan="1" rowspan="1">0.0024771</td><td colspan="1" rowspan="1">3.17</td><td colspan="1" rowspan="1">0.00076219</td><td colspan="1" rowspan="1">3.53</td><td colspan="1" rowspan="1">0.00020778</td></tr><tr><td colspan="1" rowspan="1">2.10</td><td colspan="1" rowspan="1">0.017864</td><td colspan="1" rowspan="1">2.46</td><td colspan="1" rowspan="1">0.0069469</td><td colspan="1" rowspan="1">2.82</td><td colspan="1" rowspan="1">0.0024012</td><td colspan="1" rowspan="1">3.18</td><td colspan="1" rowspan="1">0.00073638</td><td colspan="1" rowspan="1">3.54</td><td colspan="1" rowspan="1">0.00020006</td></tr><tr><td colspan="1" rowspan="1">2.11</td><td colspan="1" rowspan="1">0.017429</td><td colspan="1" rowspan="1">2.47</td><td colspan="1" rowspan="1">0.0067557</td><td colspan="1" rowspan="1">2.83</td><td colspan="1" rowspan="1">0.0023274</td><td colspan="1" rowspan="1">3.19</td><td colspan="1" rowspan="1">0.00071136</td><td colspan="1" rowspan="1">3.55</td><td colspan="1" rowspan="1">0.00019262</td></tr><tr><td colspan="1" rowspan="1">2.12</td><td colspan="1" rowspan="1">0.017003</td><td colspan="1" rowspan="1">2.48</td><td colspan="1" rowspan="1">0.0065691</td><td colspan="1" rowspan="1">2.84</td><td colspan="1" rowspan="1">0.0022557</td><td colspan="1" rowspan="1">3.20</td><td colspan="1" rowspan="1">0.00068714</td><td colspan="1" rowspan="1">3.56</td><td colspan="1" rowspan="1">0.00018543</td></tr><tr><td colspan="1" rowspan="1">2.13</td><td colspan="1" rowspan="1">0.016586</td><td colspan="1" rowspan="1">2.49</td><td colspan="1" rowspan="1">0.0063872</td><td colspan="1" rowspan="1">2.85</td><td colspan="1" rowspan="1">0.0021860</td><td colspan="1" rowspan="1">3.21</td><td colspan="1" rowspan="1">0.00066367</td><td colspan="1" rowspan="1">3.57</td><td colspan="1" rowspan="1">0.00017849</td></tr><tr><td colspan="1" rowspan="1">2.14</td><td colspan="1" rowspan="1">0.016177</td><td colspan="1" rowspan="1">2.50</td><td colspan="1" rowspan="1">0.0062097</td><td colspan="1" rowspan="1">2.86</td><td colspan="1" rowspan="1">0.0021182</td><td colspan="1" rowspan="1">3.22</td><td colspan="1" rowspan="1">0.00064095</td><td colspan="1" rowspan="1">3.58</td><td colspan="1" rowspan="1">0.00017180</td></tr><tr><td colspan="1" rowspan="1">2.15</td><td colspan="1" rowspan="1">0.015778</td><td colspan="1" rowspan="1">2.51</td><td colspan="1" rowspan="1">0.0060366</td><td colspan="1" rowspan="1">2.87</td><td colspan="1" rowspan="1">0.0020524</td><td colspan="1" rowspan="1">3.23</td><td colspan="1" rowspan="1">0.00061895</td><td colspan="1" rowspan="1">3.59</td><td colspan="1" rowspan="1">0.00016534</td></tr></table>


## 附录 B：重要数学公式

本附录列出了本书在分析硬盘驱动器信号处理系统时经常用到的数学公式。

### B.1 三角函数 (Trigonometric)

$$
\sin(-\alpha) = -\sin(\alpha)
$$

$$
\cos(-\alpha) = \cos(\alpha)
$$

$$
\sin(\alpha) = \cos(\alpha - \pi/2)
$$

$$
\sin^2(\alpha) + \cos^2(\alpha) = 1
$$

$$
\sin(\alpha \pm \beta) = \sin(\alpha)\cos(\beta) \pm \cos(\alpha)\sin(\beta)
$$

$$
\cos(\alpha \pm \beta) = \cos(\alpha)\cos(\beta) \mp \sin(\alpha)\sin(\beta)
$$

$$
\sin(\alpha)\sin(\beta) = \frac{1}{2}\cos(\alpha - \beta) - \frac{1}{2}\cos(\alpha + \beta)
$$

$$
\sin(\alpha)\cos(\beta) = \frac{1}{2}\sin(\alpha + \beta) + \frac{1}{2}\sin(\alpha - \beta)
$$

$$
\cos(\alpha)\cos(\beta) = \frac{1}{2}\cos(\alpha - \beta) + \frac{1}{2}\cos(\alpha + \beta)
$$

$$
\cos(\alpha)\sin(\beta) = \frac{1}{2}\sin(\alpha + \beta) - \frac{1}{2}\sin(\alpha - \beta)
$$

$$
\begin{array}{ll}
\sin(2\alpha) = 2\sin(\alpha)\cos(\alpha) \\
\cos(2\alpha) = \cos^2(\alpha) - \sin^2(\alpha) = 1 - 2\sin^2(\alpha) = 2\cos^2(\alpha) - 1 \\
\sin^2(\alpha) = \frac{1}{2}\{1 - \cos(2\alpha)\} \\
\cos^2(\alpha) = \frac{1}{2}\{1 + \cos(2\alpha)\} \\
e^{j\alpha} = \cos(\alpha) + j\sin(\alpha) \\
\sin(\alpha) = (e^{j\alpha} - e^{-j\alpha}) / (2j) \\
\cos(\alpha) = (e^{j\alpha} + e^{-j\alpha}) / 2
\end{array}
$$

### B.2 不定积分 (Indefinite Integral)

$$
\int u \, dv = uv - \int v \, du \quad (\text{其中 } u \text{ 和 } v \text{ 是 } x \text{ 的函数})
$$

$$
\int x^n \, dx = \frac{x^{n+1}}{n+1} \quad (n \neq -1)
$$

$$
\int x^{-1} \, dx = \ln(x)
$$

$$
\int e^{ax} \, dx = \frac{e^{ax}}{a}
$$

$$
\int \ln(x) \, dx = x \ln(x) - x
$$

$$
\int x e^{ax} \, dx = \frac{e^{ax}(ax - 1)}{a^2}
$$

$$
\int x^2 e^{ax} \, dx = \frac{e^{ax}(a^2x^2 - 2ax + 2)}{a^3}
$$

$$
\int \sin(ax) \, dx = -\frac{1}{a} \cos(ax)
$$

$$
\int \cos(ax) \, dx = \frac{1}{a} \sin(ax)
$$

$$
\int \sin^2(ax) \, dx = \frac{x}{2} - \frac{\sin(2ax)}{4a}
$$

$$
\int x \sin(ax) \, dx = \frac{1}{a^2}\{\sin(ax) - ax \cos(ax)\}
$$

$$
\int \cos^2(ax) \, dx = \frac{x}{2} + \frac{\sin(2ax)}{4a}
$$

$$
\int x \cos(ax) \, dx = \frac{1}{a^2}\{\cos(ax) + ax \sin(ax)\}
$$

## 附录 C：技术术语表

| 泰文                                                                                        | 英文                                                  | 中文                      |
| ----------------------------------------------------------------------------------------- | --------------------------------------------------- | ----------------------- |
| กฎการตัดสินใจ                                                                             | decision rule                                       | 决策准则                    |
| กระบวนการเขียน                                                                            | write process                                       | 写入过程                    |
| กระบวนการสร้างสัญญาณแอนะ ล็อกให้กลับคืนมา                                                 | signal reconstruction process                       | 信号重建过程                  |
| กระบวนการสุ่ม                                                                             | random process                                      | 随机过程                    |
| กระบวนการสุ่มเกาส์เซียน                                                                   | Gaussian random process                             | 高斯随机过程                  |
| กระบวนการอ่าน                                                                             | read process                                        | 读取过程                    |
| กระ แสไฟฟ้าสำหรับเขียนข้อมูล                                                              | write current                                       | 写入电流                    |
| กลุ่มข้อมูล                                                                               | data packet                                         | 数据包                     |
| การกลำรหัสพัลส์                                                                           | PCM (pulse code modulation)                         | 脉冲编码调制 (PCM)            |
| การกล้ำสัญญาณ (การมอดูเลต)                                                                | modulation                                          | 调制                      |
| การกล้ำ แอมพลิจูดของพัลส์                                                                 | PAM (pulse amplitude modulation)                    | 脉冲幅度调制 (PAM)            |
| การขยายสัญญาณรบกวน                                                                        | noise enhancement                                   | 噪声增强                    |
| การเข้าจังหวะ                                                                             | synchronization                                     | 同步                      |
| การเข้าจังหวะอย่างสมบูรณ์                                                                 | perfect synchronization                             | 完全同步                    |
| การเข้าถึงแบบสุ่ม                                                                         | random access                                       | 随机访问                    |
| การคาดหมาย (ค่าคาดหมาย)                                                                   | expectation                                         | 期望 (期望值)                |
| การจัดเก็บข้อมูล                                                                          | data storage                                        | 数据存储                    |
| การจัดเก็บข้อมูลดิจิทัล                                                                   | digital data storage                                | 数字数据存储                  |
| การจำลอง                                                                                  | simulation                                          | 仿真                      |
| การแจงหน่วย                                                                               | quantization                                        | 量化                      |
| การฉาย                                                                                    | projection                                          | 投影                      |
| การชดเชยก่อนการเขียน                                                                      | write precompensation                               | 写前补偿                    |
| การชักตัวอย่าง                                                                            | sampling                                            | 采样                      |
| การตรวจหาลำดับ                                                                            | sequence detection                                  | 序列检测                    |
| การทดสอบอัตราส่วนความน่าเป็นจริง                                                          | likelihood ratio test                               | 似然比测试                   |
| การทำคอนโวลูชันทางความถี                                                                  | convolution in frequency                            | 频域卷积                    |
| การทำคอนโวลูชันทางเวลา                                                                    | convolution in time                                 | 时域卷积                    |
| การทำคอนโวลูชันที่ต่อเนื่องทางเวลา                                                        | continuous-time convolution                         | 连续时间卷积                  |
| การทำคอนโวลูชันที่ไม่ต่อเนื่องทางเวลา                                                     | discrete-time convolution                           | 离散时间卷积                  |
| การแทรกสอด                                                                                | interference                                        | 干扰                      |
| การแทรกสอดระหว่างสัญลักษณ์ | ISI (intersymbol interference) | 码间干扰 (ISI) |
| การบันทึก | recording | 记录 |
| การบันทึกทับ (การเขียนทับ) | overwrite | 覆盖写入 |
| การบันทึกแบบแนวตั้ง | perpendicular recording | 垂直记录 |
| การบันทึกแบบแนวนอน | longitudinal recording | 纵向记录 |
| การบันทึกแบบไบนารี | binary recording | 二进制记录 |
| การบันทึกแบบไฮบริด | hybrid recording | 混合记录 |
| การบันทึกระบบแม่เหล็ก | magnetic recording | 磁记录 |
| การบันทึกระบบแม่เหล็กที่ใช้ความร้อนเข้าช่วย | HAMR (heat-assisted magnetic recording) | 热辅助磁记录 (HAMR) |
| การบีบเวลา | time-compression | 时间压缩 |
| การประมวลผลสัญญาณดิจิทัล | digital signal processing | 数字信号处理 (DSP) |
| การเปลี่ยนสถานะ | transition | 状态转移 |
| การเปลียนสถานะเอกเทศ | isolated transition | 孤立状态转移 |
| การแปลงซี | Z transform | Z 变换 |
| การแปลงฟูเรียร์ | Fourier transform | 傅里叶变换 |
| การแปลงฟูเรียร์ผกผัน | inverse Fourier transform | 逆傅里叶变换 |
| การแพร่กระจายของข้อผิดพลาด | error propagation | 错误传播 |
| การแยกสัญญาณ (ดีมอดูเลชัน) | demodulation | 解调 |
| การลดทอน | attenuation | 衰减 |
| การลบล้างบางส่วน | partial erasure | 部分擦除 |
| การลบล้างสภาพแม่เหล็ก | demagnetization | 消磁 |
| การเลื่อนขนานเชิงความถี่ | translation | 平移 |
| การเลื่อนตำแหน่งของการเปลี่ยนสถานะ | transition shift | 转移偏移 |
| การเลื่อนตำแหน่งของการเปลี่ยนสถานะ แบบแข็ง | HTS (hard transition shift) | 硬转移偏移 (HTS) |
| การเลื่อนตำแหน่งของการเปลี่ยนสถานะ แบบไม่เป็นเชิงเส้น | NLTS (nonlinear transition shift) | 非线性转移偏移 (NLTS) |
| การเลื่อนตำแหน่งของการเปลี่ยนสถานะ แบบอ่อน | ETS (easy transition shift) | 软转移偏移 (ETS) |
| การเลื่อนทางความถี่ | frequency shifting | 频移 |
| การเลื่อนทางเวลา | time shifting | 时移 |
| การสูญเสียแอมพลิจูดแบบไม่เป็นเชิงเส้น | nonlinear amplitude loss | 非线性幅度损失 |
| การเสื่อม | degradation | 恶化 / 退化 |
| การหน่วงเวลาการตัดสินใจ | decision delay | 决策延迟 |
| การหาปริพันธ์ทางเวลา | time integration | 时间积分 |
| การหาอนุพันธ์ | differentiation | 微分 |
| การหอนุพันธ์ทางเวลา | time differentiation | 时间微分 |
| กำลัง | power | 功率 |
| กำลังขณะหนึ่ง | instantaneous power | 瞬时功率 |
| กำลังเฉลี่ย | average power | 平均功率 |
| กำลังเฉลี่ยทางเวลา | time-averaged power | 时间平均功率 |
| กำ ลังสองเฉลี่ยที่น้อยสุด | LMS (least mean square) | 最小均方 (LMS) |
| กิกะบิต | Gb (gigabit) | Gb (千兆比特) |
| กิกะไบต์ | GB (gigabyte) | GB (千兆字节) |
| เกรน, เม็ด, เนื้อ | grain | 晶粒 |
| เกาส์เซียน | Gaussian | 高斯 |
| ขนาด | magnitude | 幅值 / 大小 |
| ขอบเขตของสัญญาณรบกวน | noise margin | 噪声裕量 |
| ข้อผิดพลาด | error | 错误 |
| ข้อผิดพลาดการแจงหน่วย | quantization error | 量化误差 |
| ข้อผิดพลาดกำ ลังสองเฉลี่ย | MSE (mean-squared error) | 均方误差 (MSE) |
| ข้อผิดพลาดกำ ลังสองเฉลี่ยที่น้อยสุด | MMsE (minimum mean-squared error) | 最小均方误差 (MMSE) |
| ข้อมูลไบนารี | binary data | 二进制数据 |
| ข้อมูลวิยุต (แซมเปิล) | discrete data | 离散数据 (样本) |
| ควรจะ เป็uมากสุด | ML (maximum-likelihood) | 最大似然 (ML) |
| ความกว้างของแทร็ก | track width | 磁道宽度 |
| ความขรุขระเชิงความร้อน | thermal asperity | 热凸起 |
| ความเข้มของพลังงาน | energy intensity | 能量强度 |
| ความจุช่องสัญญาณ | channel capacity | 信道容量 |
| ความถีการชักตัวอย่าง | sampling frequency | 采样频率 |
| ความถี่เชิงมุม | angular frequency | 角频率 |
| ความถี่ตัด | cut-off frequency | 截止频率 |
| ความถี่ไนควิตส์ | Nyquist frequency | 奈奎斯特频率 |
| ความถี่มูลฐาน | fundamental frequency | 基频 |
| ความน่าจะ เป็น | probability | 概率 |
| ความน่าจะ เป็นของข้อผิดพลาด | probability of error | 误码率 |
| ความแปรปรวน | variance | 方差 |
| ความแปรปรวนร่วมเกี่ยว | covariance | 协方差 |
| ความผิดเพี้ยนของค่าสูงสุด | peak distortion | 峰值畸变 |
| ความผิดเพียนจุดตัดค่าศูนย์ | distortion of zero crossings | 零点交叉畸变 |
| ความผิดเพี้ยนเชิงแบบเชิงเส้น | linear distortion | 线性畸变 |
| ความผิดเพี้ยนเชิงเฟส | phase distortion | 相位畸变 |
| ความผิดเพี้ยนเชิงแอมพลิจูด | amplitude distortion | 幅度畸变 |
| ความผิดเพี้ยนแบบไม่เชิงเส้น | nonlinear distortion | 非线性畸变 |
| ความผิดเพี้ยนภาพ | aliasing | 混叠 |
| ความไม่เป็นเชิงเส้น | nonlinearity | 非线性 |
| ความไวต่อข้อผิดพลาดทางเวลา | sensitivity timing error | 定时误差敏感度 |
| ความสัมพันธ์ของพาร์ซิวาล | Parseval's relation | 帕塞瓦尔关系 |
| ความสุ่ม | randomness | 随机性 |
| ความหนาแน่นของการบันทึกแบบนอร์มอลไลซ์ | ND (normalized recording density) | 归一化记录密度 (ND) |
| ความหนาแน่นเชิงแทร็ก | track density | 磁道密度 |
| ความหนาแน่นเชิงพื้นที่ | areal density | 面密度 |
| ความหนาแน่นเชิงเส้น | linear density | 线密度 |
| ความหนาแน่นสเปกตรัม | spectral density | 频谱密度 |
| ความหนาแน่นสเปกตรมกำลัง | power spectral density | 功率谱密度 |
| ความหนาแน่นสเปกตรัมพลังงาน | energy spectral density | 能量谱密度 |
| ความไหว | sensitivity | 灵敏度 |
| คอนโวลูชัน | convolution | 卷积 |
| ค่ากำลังสองเฉลี่ย | mean square | 均方值 |
| ค่าคาดหมาย (ค่าเฉลีย) | expected value | 期望值 |
| ค่าเฉลี่ย | mean | 平均值 |
| ค่าเฉลี่ยของตัวอย่าง | sample mean | 样本平均值 |
| ค่าเฉลี่ยทางเวลา | time average | 时间平均 |
| ค่าเฉลี่ยทางสถิติ | statistic average | 统计平均 |
| ค่าเฉลี่ยเอนเซมเบิล (ค่าเฉลี่ยทั้งชุด) | ensemble average | 统计平均 (Ensemble Average) |
| ค่าตัดสินใจ | decision | 决策 |
| คาบ (เวลา) | period | 周期 |
| คาบการชักตัวอย่าง | sampling period | 采样周期 |
| คาบมูลฐาน | fundamental period | 基周期 |
| คาบเวลาของบิต | bit period | 比特周期 |
| ค่าสัมประสิทธิ์ของอีควอไลเซอร์ที่เหมาะที่สุด | optimum coefficient | 最优系数 |
| ค่าสัมประสิทธิ์แอนไอโซทรอปีแบบแกนเดี่ยว | uniaxial anisotropy coefficient | 单轴各向异性系数 |
| คุณสมบัติการแจกแจง | distributive property | 分配律 |
| คุณสมบัติการซ้อนทับ | superposition property | 叠加原理 |
| คุณสมบัติการบวก | additivity property | 可加性 |
| คุณสมบัติการเปลี่ยนหมู่ | associative property | 结合律 |
| คุณสมบัติการสลับที่ | commutative property | 交换律 |
| คุณสมบัติคอซอลิดี้ | causality property | 因果性 |
| คุณสมบัติซิฟต์ทิง | sifting property | 筛选特性 |
| คุณสมบัติทวิภาวะ | duality property | 对偶性 |
| คุณสมบัติสเตชันเนรี | stationary | 平稳性 |
| คุณสมบัติเอกพันธ์ | scaling property (homogeneity) | 齐次性 / 尺度不变性 |
| คุณสมบัติเออร์กอดิก | ergodicity | 各态历经性 |
| คู่การแปลงฟูเรียร์ | Fourier transform pair | 傅里叶变换对 |
| แถบบันทึก (แถบ)                                                                           | tape                                                | 磁带                      |
| แถบบันทึกกระดาษ                                                                           | paper tape                                          | 纸带                      |
| แถบแม่เหล็ก                                                                               | magnetic tape                                       | 磁带                      |
| แถวลำดับ (อะเรย์)                                                                         | array                                               | 数组                      |
| ทฤษฎีบทการ ชักตัวอย่าง                                                                    | sampling theorem                                    | 采样定理                    |
| ทฤษฎีบทการ ชักตัวอย่างของในควิตส์                                                         | Nyquist's sampling theorem                          | 奈奎斯特采样定理                |
| ทฤษฎีบทของเบส์                                                                            | Bayes' theorem                                      | 贝叶斯定理                   |
| ทฤษฎีบทพลังงานของเรย์ลี                                                                   | Rayleigh's energy theorem                           | 瑞利能量定理                  |
| ทาร์เก็ต                                                                                  | target                                              | 目标响应                    |
| ทาร์เก็ตแบบ GPR                                                                           | generalized partial-response (GPR) target           | 广义部分响应 (GPR) 目标         |
| ทาร์เก็ตแบบ PR                                                                            | partial-response target                             | 部分响应 (PR) 目标            |
| ทำให้เป็นบรรทัดฐาน                                                                        | normalize                                           | 归一化                     |
| เทคนิคการบังคับให้เป็นศูนย์                                                               | zero-forcing technique                              | 零强制技术                   |
| เทระไบต์                                                                                  | TB (terabyte)                                       | TB (太字节)                |
| แท็ป                                                                                      | tap                                                 | 抽头                      |
| แทร็ก (วง หรือ ร่อง)                                                                      | track                                               | 磁道                      |
| ไทมมิ่งริ คัฟเวอรี                                                                        | timing recovery                                     | 定时恢复                    |
| บัตรเจาะรู                                                                                | punch card                                          | 打孔卡                     |
| บิต                                                                                       | bit                                                 | 比特                      |
| บิตข่าวสาร                                                                                | message bit                                         | 信息比特                    |
| บิตเซลล์ T (คาบเวลาของหนึ่งบิต)                                                           | bit cell                                            | 比特单元 (bit cell)         |
| บิตเปลี่ยนสถานะ                                                                           | transition bit                                      | 状态转移比特                  |
| บิตส่วนเกิน                                                                               | redundant bit                                       | 冗余比特                    |
| แบนด์วิดท์                                                                                | bandwidth                                           | 带宽                      |
| แบนด์วิดท์แบบศูนย์ถึงศูนย์                                                                | null-to-null bandwidth                              | 零到零带宽                   |
| แบบข้อมูล                                                                                 | data pattern                                        | 数据模式                    |
| แบบจำลอง                                                                                  | model                                               | 模型                      |
| แบบจำ ลองช่องสัญญาณที่ไม่ต่อเนื่องทางเวลาแบบสมมูล                                         | equivalent discrete-time channel model              | 等效离散时间信道模型              |
| ไบต์ (1 ไบต์ = 8 บิต)                                                                     | byte                                                | 字节                      |
| ไบนารี (ฐานสอง)                                                                           | binary                                              | 二进制                     |
| ประเภทของหัวแม่เหล็กชนิดหนึ่ง                                                             | MR (magneto-resistive)                              | 磁电阻 (MR) 头              |
| ประสิทธิภาพแบนด์วิดท์                                                                     | bandwidth efficiency                                | 带宽效率                    |
| ปรับ (ให้เป็นปัจจุบัน)                                                                    | update                                              | 更新                      |
| ปริภูมิตัวอย่าง                                                                           | sample space                                        | 样本空间                    |
| ผลตอบสนอง                                                                                 | response                                            | 响应                      |
| ผลตอบสนองการเปลี่ยนสถานะ                                                                  | transition response                                 | 转移响应                    |
| ผลตอบสนองของระบบ                                                                          | system response                                     | 系统响应                    |
| ผลตอบสนองเชิงความถี่                                                                      | frequency response                                  | 频率响应                    |
| ผลตอบสนองไดบิต                                                                            | dibit response                                      | 双比特响应                   |
| ผลตอบสนองบางส่วน                                                                          | PR (partial response)                               | 部分响应 (PR)               |
| ผลตอบสนองบางส่วนควรจะ เป็นมากสุด                                                          | PRML (partial-response maximum-likelihood)          | 部分响应最大似然 (PRML)         |
| ผลตอบสนองบางส่วนแบบทั่วไป                                                                 | GPR (generalized partial-response)                  | 广义部分响应 (GPR)            |
| ผลตอบสนองอิมพัลส์                                                                         | impulse response                                    | 冲激响应                    |
| แผงควบคุมวงจรไฟฟ้า                                                                        | printed circuit board                               | 印制电路板 (PCB)             |
| แผ่นชีดี                                                                                  | CD (compact disc)                                   | CD (紧凑光盘)               |
| แผ่นดีวีดี                                                                                | DVD (digital versatile disc)                        | DVD (数字多功能光盘)           |
| แผ่นบันทึก                                                                                | floppy disk                                         | 软盘                      |
| แผ่นบันทึกแม่เหล็ก                                                                        | magnetic floppy disk                                | 磁性软盘                    |
| แผนภาพ                                                                                    | diagram                                             | 图表 / 示意图                |
| แผนภาพดวงตา                                                                               | eye diagram                                         | 眼图                      |
| พฤติกรรมเชิงเฉลี่ย                                                                        | average behavior                                    | 平均行为                    |
| พลังงาน                                                                                   | energy                                              | 能量                      |
| พลังงานเชิงความร้อน                                                                       | thermal energy                                      | 热能                      |
| พลังงานบิตเฉลี่ย                                                                          | average bit energy                                  | 平均比特能量                  |
| พลังงานหนึ่งหน่วย                                                                         | unit energy                                         | 单位能量                    |
| พหุนาม                                                                                    | polynomial                                          | 多项式                     |
| พื้นข้อผิดพลาด                                                                            | error floor                                         | 错误底                     |
| โพรบ (หัวตรวจ)                                                                            | probe                                               | 探针                      |
| ฟลักซ์                                                                                    | flux                                                | 磁通量                     |
| ฟังก์ชัน                                                                                  | function                                            | 函数                      |
| ฟังก์ชันก่อกำเนิด                                                                         | generating function                                 | 生成函数                    |
| ฟังก์ ชันการ แจกแจงความน่าจะ เป็น                                                         | cumulative distribution function                    | 累积分布函数 (CDF)            |
| ฟังก์ ชันการชักตัวอย่าง                                                                   | sampling function                                   | 采样函数                    |
| ฟังก์ชันกำ ลังสอง                                                                         | quadratic function                                  | 二次函数                    |
| ฟังก์ชันขั้นหนึ่งหน่วย                                                                    | unit step function                                  | 单位阶跃函数                  |
| ฟังก์ ชันความหนาแน่นความน่าจะเป็น                                                         | probability density function                        | 概率密度函数 (PDF)            |
| ฟังก์ชันความหนาแน่นความน่าจะเป็นก่อน                                                      | a-priori probability density function               | 先验概率密度函数                |
| ฟังก์ ชันความหนาแน่นความน่าจะเป็นแบบเกาส์เซียน                                            | Gaussian probability density function               | 高斯概率密度函数                |
| ฟังก์ ชันความหนาแน่นความน่าจะเป็นมีเงื่อนไข                                               | conditional probability density function            | 条件概率密度函数                |
| ฟังก์ชันคู่                                                                               | even function                                       | 偶函数                     |
| ฟังก์ชันโครเนคเกอร์ เดลตา                                                                 | Kronecker delta function                            | 克罗内克 $\delta$ 函数        |
| ฟังก์ชันซิงก์                                                                             | sinc function                                       | sinc 函数                 |
| ฟังก์ ชันเดลตา                                                                            | Delta function                                      | $\delta$ 函数             |
| ฟังก์ชันไดเรคเดลตา                                                                        | Dirac delta function                                | 狄拉克 $\delta$ 函数         |
| ฟังก์ ชันถ่ายโอน                                                                          | transfer function                                   | 传递函数                    |
| ฟังก์ ชันอัตสหสัมพันธ์เฉลี่ยทางเวลา                                                       | time-averaged auto-correlation function             | 时间平均自相关函数               |
| ฟังก์ชันอิมพัลส์                                                                          | impulse function                                    | 冲激函数                    |
| ฟิล์มบาง                                                                                  | thin film                                           | 薄膜                      |
| เฟร์ไรต์                                                                                  | ferrite                                             | 铁氧体                     |
| ไฟฟ้ากระแสตรง                                                                             | d.c. (direct current)                               | 直流电 (DC)                |
| ภาวะ                                                                                      | mode                                                | 模式                      |
| ภาวะการได้มา                                                                              | acquisition mode                                    | 捕获模式                    |
| ภาวะการติดตาม                                                                             | tracking mode                                       | 跟踪模式                    |
| ภาวะการฝึกอบรม                                                                            | training mode                                       | 训练模式                    |
| ภาวะ เกรนหยาบ (สภาพการเป็นเม็ด) | granularity | 晶粒度 |
| มอเตอร์สปินเดิล (มอเตอร์กระสวย) | spindle motor | 主轴电机 |
| มัลติเพล็กซ์ (สหสัญญาณ)                                                                   | multiplex                                           | 多路复用                    |
| เมกะไบต์                                                                                  | MB (megabyte)                                       | MB (兆字节)                |
| เมทริกซ์อัตสหสัมพันธ์                                                                     | auto-correlation matrix                             | 自相关矩阵                   |
| ไมโครโพรเซสเซอร์                                                                          | microprocessor                                      | 微处理器                    |
| ไม่มีสหสัมพันธ์กัน                                                                        | uncorrelated                                        | 无相关                     |
| รหัส RLL                                                                                  | run-length limited (RLL) code                       | 运行长度受限 (RLL) 码          |
| ร หัสแก้ไขข้อผิดพลาด                                                                      | ECC (error-correction code)                         | 纠错码 (ECC)               |
| รหัสมอดูเลชัน                                                                             | modulation code                                     | 调制码                     |
| ระดับการแจงหน่วย                                                                          | quantization level                                  | 量化级                     |
| ระบบการจัดเก็บข้อมูล                                                                      | data storage system                                 | 数据存储系统                  |
| ระบบการบันทึกแบบแนวตั้ง                                                                   | perpendicular recording system                      | 垂直记录系统                  |
| ระบบการบันทึกแบบแนวนอน                                                                    | longitudinal recording system                       | 纵向记录系统                  |
| ระบบการบันทึกแม่เหล็ก                                                                     | magnetic recording system                           | 磁记录系统                   |
| ระบบการส่งสัญญาณแถบความถี่ฐาน                                                             | baseband transmission system                        | 基带传输系统                  |
| ระบบเชิงเส้นที่ไม่แปร เปลี่ยนตามเวลา                                                      | linear time-invariant (LTI) system                  | 线性时不变 (LTI) 系统          |
| ระบบที่ไม่ต่อเนื่องทางเวลา                                                                | discrete-time system                                | 离散时间系统                  |
| ระบบที่ไม่แปรเปลี่ยนตามเวลา                                                               | time-invariant system                               | 时不变系统                   |
| ระบบที่สามารถส่งผ่านสัญญาณได้โดยไม่ผิดเพียน                                               | distortionless system                               | 无畸变系统                   |
| ระบบไบนารี                                                                                | binary system                                       | 二进制系统                   |
| ระบบสือสาร                                                                                | communication system                                | 通信系统                    |
| ระบบสื่อสารดิจิทัล                                                                        | digital communication system                        | 数字通信系统                  |
| ระยะทางกำลังสองเฉลี่ย                                                                     | MSD (mean-squared distance)                         | 均方距离 (MSD)              |
| รูปคลื่น                                                                                  | waveform                                            | 波形                      |
| รูปแบบข้อมูล                                                                              | data format                                         | 数据格式                    |
| เรจิสเตอร์แบบเลื่อน                                                                       | shift register                                      | 移位寄存器                   |
| ล่วงหน้าเวลา                                                                              | advance                                             | 超前                      |
| ลำดับ                                                                                     | sequence                                            | 序列                      |
| ลำดับข้อมู ล                                                                              | data sequence                                       | 数据序列                    |
| ลำดับข้อมูลเปลี่ยนสถานะ                                                                   | transition data sequence                            | 状态转移数据序列                |
| ลิมิตแชนนอน                                                                               | Shannon limit                                       | 香农极限                    |
| ลูปฮิสเทอรีซิส                                                                            | Hysteresis loop                                     | 磁滞回线                    |
| เลื่อนเวลา                                                                                | time-shift                                          | 时移                      |
| ไลน์โค้ด                                                                                  | line code                                           | 线码                      |
| วงจรกรอง                                                                                  | filter                                              | 滤波器                     |
| วงจรกรองแบบเชิงเส้น                                                                       | linear filter                                       | 线性滤波器                   |
| วงจรกรองผ่านตำ                                                                            | LPF (low-pass filter)                               | 低通滤波器 (LPF)             |
| วงจรกรองผ่านตำอุดมคติ                                                                     | ideal low-pass filter                               | 理想低通滤波器                 |
| วงจรกรองภาครับ                                                                            | receiving filter                                    | 接收滤波器                   |
| วงจรกรองภาคส่ง                                                                            | transmitting filter                                 | 发送滤波器                   |
| วงจรกรองเหมาะสุด                                                                          | matched filter                                      | 匹配滤波器                   |
| วงจรขยายก่อน                                                                              | pre-amplifier                                       | 前置放大器                   |
| วงจรขยายแบบแปรผันได้                                                                      | VGA (variable gain amplifier)                       | 可变增益放大器 (VGA)           |
| วงจรเข้ารหัส                                                                              | encoder                                             | 编码器                     |
| วงจรเข้ารหัสแก้ไขข้อผิดพลาด                                                               | error-correction code (ECC) encoder                 | 纠错码 (ECC) 编码器           |
| วงจรเข้ารหัสมอดูเลชัน                                                                     | modulation encoder                                  | 调制编码器                   |
| วงจรคู่ควบไฟฟ้ากระ แสสลับ                                                                 | a.c. (alternating current) coupling                 | 交流耦合                    |
| วงจรแจงหน่วย                                                                              | quantizer                                           | 量化器                     |
| วงจรชักตัวอย่าง                                                                           | sampler                                             | 采样器                     |
| วงจรตรวจหา                                                                                | detector                                            | 检测器                     |
| วงจรตรวจหา NPML                                                                           | noise-predictive maximum-likelihood (NPML) detector | 噪声预测最大似然 (NPML) 检测器     |
| วงจรตรวจหา PRML                                                                           | partial-response maximum-likelihood (PRML) detector | 部分响应最大似然 (PRML) 检测器     |
| วงจรตรวจหาขีดเริมเปลียน                                                                   | threshold detector, slicer                          | 阈值检测器 / 切片器 (Slicer)    |
| วงจรตรวจหาจุดสูงสุด                                                                       | peak detector                                       | 峰值检测器                   |
| วงจรตรวจหาแบบ MAP                                                                         | maximum a-posteriori probability (MAP) detector     | 最大后验概率 (MAP) 检测器        |
| วงจรตรวจหาแบบ ML                                                                          | maximum-likelihood (ML) detector                    | 最大似然 (ML) 检测器           |
| วงจรตรวจหาลำ ดับที่ควรจะ เป็นมากสุด                                                       | MLsD (maximum-likelihood sequence detector)         | 最大似然序列检测器 (MLSD)        |
| วงจรตรวจหาวีเทอร์บิ                                                                       | Viterbi detector                                    | 维特比检测器                  |
| วงจรตรวจหาสัญลักษณ์                                                                       | symbol detector                                     | 符号检测器                   |
| วงจรถอดรหัส                                                                               | decoder                                             | 解码器                     |
| วงจรถอดร หัสแก้ไขข้อผิดพลาด                                                               | error-correction code (ECC) decoder                 | 纠错码 (ECC) 解码器           |
| วงจรเปลี่ยนสัญญาณแอนะ ล็อกเป็นสัญญาณดิจิทัล                                               | ADC (analog-to-digital converter)                   | 模数转换器 (ADC)             |
| วงจรเฟสล็อกลูป                                                                            | PLL (phase-locked loop)                             | 锁相环 (PLL)               |
| วงจรสหสัมพันธ์                                                                            | correlator                                          | 相关器                     |
| วงจรหาอนุพันธ์                                                                            | differentiator                                      | 微分器                     |
| วงที่พักหัวอ่าน/บันทึก                                                                    | landing zone                                        | 停靠区 (Landing Zone)      |
| วัสดุแม่เหล็ก                                                                             | magnetic material                                   | 磁性材料                    |
| เวกเตอร์หนึ่งหน่วย                                                                        | unit vector                                         | 单位向量                    |
| เวลาที่เหมาะที่สุดสำหรับการชักตัวอย่าง                                                    | optimum sampling time                               | 最优采样时间                  |
| โวลต์                                                                                     | volt                                                | 伏特                      |
| สเตซันเนรี แบบไวด์เซนส์                                                                   | WSS (wide-sense stationary)                         | 宽平稳 (WSS)               |
| สูเตชันเนรีแบบสตริกเซนส์                                                                  | SSS (strict-sense stationary)                       | 严平稳 (SSS)               |
| สนามแม่เหล็กของหัวเขียน                                                                   | head magnetic field                                 | 写头磁场                    |
| สนามแม่เหล็กตกค้าง                                                                        | remanent magnetic filed                             | 剩磁场                     |
| สเปกตรัม                                                                                  | spectrum                                            | 频谱                      |
| สเปกตรัมของสัญญาณ                                                                         | signal spectrum                                     | 信号频谱                    |
| สเปกตรัมค่าศูนย์                                                                          | spectral null                                       | 频谱零点                    |
| สเปกตรัมเชิงเฟส                                                                           | phase spectrum                                      | 相位谱                     |
| สเปกตรัมเชิงแอมพลิจูด                                                                     | amplitude spectrum                                  | 幅度谱                     |
| สเปกตรัมแบบเส้น                                                                           | line spectrum                                       | 线谱                      |
| สภาพความเป็นแม่เหล็ก (การทำให้เป็นแม่เหล็ก)                                               | magnetization                                       | 磁化                      |
| สภาพความเป็นแม่เหล็กของสื่อบันทึก                                                         | medium magnetization                                | 介质磁化                    |
| สภาพแม่เหล็กตกค้าง                                                                        | remanent magnetization                              | 剩磁                      |
| สภาพลบล้างแม่เหล็ก                                                                        | coercivity                                          | 矫顽力                     |
| สภาพให้ซึมผ่านได้                                                                         | permeability                                        | 磁导率                     |
| สลับเปลี่ยน (ทรานสโพส)                                                                    | transpose                                           | 转置                      |
| ส่วนประกอบ                                                                                | component                                           | 分量 / 组件                 |
| สหสัมพันธุ์                                                                               | correlation                                         | 相关性                     |
| สหสัมพันธุ์ข้าม                                                                           | cross-correlation                                   | 互相关                     |
| สังยุคเชิงซ้อน                                                                            | complex conjugate                                   | 共轭复数                    |
| สัจพจน์                                                                                   | axiom                                               | 公理                      |
| สัญญาณ                                                                                    | signal                                              | 信号                      |
| สัญญาณกระตุ้น                                                                             | excitation signal                                   | 激励信号                    |
| สัญญาณกำลัง                                                                               | power signal                                        | 功率信号                    |
| สัญญาณเชิงกำหนด                                                                           | deterministic signal                                | 确定性信号                   |
| สัญญาณตอบสนอง                                                                             | response signal                                     | 响应信号                    |
| สัญญาณแถบความถี่ฐาน                                                                       | baseband signal                                     | 基带信号                    |
| สัญญาณที่ต่อเนื่องทางเวลา                                                                 | continuous-time signal                              | 连续时间信号                  |
| สัญญาณที่มีแถบความถี่จำกัด                                                                | band-limited signal                                 | 带限信号                    |
| สัญญาณที่มีเวลาจำกัด                                                                      | time-limited signal                                 | 时限信号                    |
| สัญญาณที่ไม่ต่อเนื่องทางเวลา                                                              | discrete-time signal                                | 离散时间信号                  |
| สัญญาณไบนารี (สัญญาณสองระดับ)                                                             | binary signal                                       | 二进制信号                   |
| สัญญาณเป็นคาบ                                                                             | periodic signal                                     | 周期信号                    |
| สัญญาณพลังงาน                                                                             | energy signal                                       | 能量信号                    |
| สัญญาณพัลส์ RC                                                                            | raised-cosine pulse                                 | 升余弦脉冲                   |
| สัญญาณพัลส์ RRC                                                                           | root-raised cosine                                  | 根升余弦 (RRC)              |
| สัญญาณพัลส์ในควิตส์                                                                       | Nyquist pulse                                       | 奈奎斯特脉冲                  |
| สัญญาณพัลส์ในควิตส์อุดมคติ                                                                | ideal Nyquist pulse                                 | 理想奈奎斯特脉冲                |
| สัญญาณพัลส์เปลี่ยนสถานะ                                                                   | transition pulse                                    | 转移脉冲                    |
| สัญญาณพัลส์เปลี่ยนสถานะ เอกเทศ                                                            | isolated transition pulse                           | 孤立转移脉冲                  |
| สัญญาณพัลส์รูปดับเลต                                                                      | doublet signal                                      | 双极脉冲                    |
| สัญญาณพัลส์รูปสี่เหลี่ยม                                                                  | rectangular pulse                                   | 矩形脉冲                    |
| สัญญาณไม่เป็นคาบ                                                                          | non-periodic signal, aperiodic signal               | 非周期信号                   |
| สัญญาณรบกวน                                                                               | noise                                               | 噪声                      |
| สัญญาณรบกวนการแจงหน่วย                                                                    | quantization noise                                  | 量化噪声                    |
| สัญญาณรบกวนการเปลี่ยนสถานะ                                                                | transition noise                                    | 转移噪声                    |
| สัญญาณรบกวนเกาส์สีขาว                                                                     | white Gaussian noise                                | 高斯白噪声                   |
| สัญญาณรบกวนเกาส์สีขาวแบบบวก                                                               | AWGN (additive white Gaussian noise)                | 加性高斯白噪声 (AWGN)          |
| สัญญาณรบกวนความร้อน                                                                       | thermal noise                                       | 热噪声                     |
| สัญญาณรบกวนแบบสี                                                                          | colored noise                                       | 有色噪声                    |
| สัญญาณรบกวนสีขาว                                                                          | white noise                                         | 白噪声                     |
| สัญญาณรบกวนสื่อบันทึก                                                                     | media noise                                         | 介质噪声                    |
| สัญญาณสุ่ม                                                                                | random signal                                       | 随机信号                      |
| สัญญาณหลายระดับ                                                                           | multi-level signal                                  | 多电平信号                   |
| สัญญาณอิมพัลส์หนึ่งหน่วย                                                                  | unit impulse signal                                 | 单位冲激信号                  |
| สัญญาณแอนะ ล็อกทางไฟฟ้าที่ได้จากหัวอ่าน (สัญญาณ read-back)                                | read-back signal                                    | 读回模拟信号                  |
| สัมประสิทธิ์                                                                              | coefficient                                         | 系数                      |
| สิ่งเปรอะเปือน                                                                            | contamination                                       | 污染                      |
| สื่อบันทึก (จานแม่เหล็ก)                                                                  | media (Or medium)                                   | 记录介质 (磁碟)               |
| สื่อบันทึกแม่เหล็ก                                                                        | magnetic media                                      | 磁性介质                    |
| สูตรการประมาณค่าในช่วงของในควิตส์และ แชนนอน                                               | Nyquist-Shannon interpolation formula               | 奈奎斯特-香农插值公式             |
| เส้นเชื่อมฐาน                                                                             | baseline                                            | 基线                      |
| เสียงรบกวนจากแถบเสียง                                                                     | modulation noise                                    | 调制噪声                    |
| หน่วงเวลา                                                                                 | delay                                               | 延迟                      |
| หน่วยเก็บโพรบ                                                                             | probe storage                                       | 探针存储                    |
| หน่วยความจำของช่องสัญญาณ                                                                  | channel memory                                      | 信道存储                    |
| หน่วยความจำไม่ลบเลือน                                                                     | nonvolatile memory                                  | 非易失性存储器                 |
| หน่วยความจำลบเลือนได้                                                                     | volatile memory                                     | 易失性存储器                  |
| หน่วยความจำหลักแบบสารกึ่งตัวนำ                                                            | semiconductor main memory                           | 半导体主存储器                 |
| หัวเขียน                                                                                  | write head                                          | 写头                      |
| หัวแม่เหล็ก (หัวอ่านและหัวเขียน)                                                          | magnetic head                                       | 磁头                      |
| หัวอ่าน                                                                                   | read head                                           | 读头                      |
| เหตุการณ์                                                                                 | event                                               | 事件                      |
| เหตุการณ์ไม่เกิดร่วม                                                                      | mutually exclusive events                           | 互斥事件                    |
| เหมาะที่สุด                                                                               | optimal                                             | 最优的                     |
| แหล่งต้นทาง                                                                               | source                                              | 信源 / 源端                 |
| แหล่งปลายทาง                                                                              | destination                                         | 信宿 / 目的端                |
| อนุภาค (ละอองธุลี)                                                                        | particulate                                         | 微粒                      |
| อสมการชวาร์ซ                                                                              | Schwarz's inequality                                | 施瓦茨不等式                  |
| อัตความแปรปรวนร่วมเกี่ยว                                                                  | auto-covariance                                     | 自协方差                    |
| อัตราการขยาย                                                                              | gain                                                | 增益                      |
| อัตราการขยายการเข้ารหัส                                                                   | coding gain                                         | 编码增益                    |
| อัตราการ ชักตัวอย่าง                                                                      | sampling rate                                       | 采样率                     |
| อัตราการ ลู่เข้า                                                                          | convergence rate                                    | 收敛速度                    |
| อัตราข้อผิดพลาดบิต                                                                        | BER (bit-error rate)                                | 误比特率 (BER)              |
| อัตราเจริ ญเติบโต (รายปี) ทบต้น                                                           | CGR (compound growth rate)                          | 复合增长率 (CGR)             |
| อัตราบิต                                                                                  | bit rate                                            | 比特率                     |
| อัตรารหัส                                                                                 | code rate                                           | 码率                      |
| อัตราส่งข้อมูล                                                                            | data rate                                           | 数据传输率                   |
| อัตราส่วนค่ากำลังเฉ ลี่ยของสัญญาณที่ต้องการต่อค่ากำ ลังเฉ ลี่ยของสัญญาณรบกวน              | SNR (signal-to-noise ratio)                         | 信噪比 (SNR)               |
| อัตราส่วนค่ากำลังเฉ ลี่ยของสัญญาณที่ต้องการ ต่อค่ากำ ลังเฉ ลี่ยของสัญญาณรบกวนการ แจงหน่วย | SQNR (signa to-quantization noise ratio)            | 信量化噪声比 (SQNR)           |
| อัตสหสัมพันธ์                                                                             | auto-correlation                                    | 自相关                     |
| อัลกอริทึม (ขั้นตอนวิธี)                                                                  | algorithm                                           | 算法                      |
| อัลกอริทึม steepest descent                                                               | steepest descent algorithm                          | 最速下降算法                  |
| อัลกอริทึมเกรเดียนต์                                                                      | gradient algorithm                                  | 梯度算法                    |
| อัลกอริทึมวีเทอร์บิ                                                                       | Viterbi algorithm                                   | 维特比算法                   |
| อินดักทีฟ (ประเภทของหัวอ่าน)                                                              | inductive                                           | 电感式                     |
| อินพุต (รับเข้า, นำเข้า)                                                                  | input                                               | 输入                      |
| อิ่มตัว                                                                                   | saturated                                           | 饱和                      |
| อิสระกันเชิงสถิติ                                                                         | statistically independent                           | 统计独立                    |
| อีควอไลเซอร์                                                                              | equalizer                                           | 均衡器                     |
| อีควอไลเซอร์แบบ TDL                                                                       | tapped-delay-line (TDL) equalizer                   | 抽头延迟线 (TDL) 均衡器         |
| อีควอไลเซอร์ แบบปรับตัว                                                                   | adaptive equalizer                                  | 自适应均衡器                  |
| อีควอไลเซอร์แบบเส้นตัดขวาง                                                                | transversal equalizer                               | 横向均衡器                   |
| อุปกรณ์เก็บข้อมูลเชิงแสง                                                                  | optical storage device                              | 光存储设备                   |
| เอนเซมเบิล                                                                                | ensemble                                            | 统计集 / 全集                |
| เอนทิดี                                                                                   | entity                                              | 实体                      |
| เอาต์พุต (ส่งออก, นำออก)                                                                  | output                                              | 输出                      |
| เอาต์พุตของช่องสัญญาณ                                                                     | channel output                                      | 信道输出                    |
| แอนไอโซทรอปี                                                                              | anisotropy                                          | 各向异性                    |
| แอนะ ล็อก                                                                                 | analog                                              | 模拟                      |
| แอมพลิจูด                                                                                 | amplitude                                           | 幅度                      |
| ฮอโลกราฟี                                                                                 | holography                                          | 全息术                     |
| ฮาร์ดดิสก์ไดรฟ์                                                                           | hard disk drive                                     | 硬盘驱动器 (HDD)             |
| เฮิรตซ์                                                                                   | Hz (hertz)                                          | 赫兹 (Hz)                 |
| เครือข่าย                                                                                 | network                                             | 网络                      |
| เครือข่ายเฉพาะที                                                                          | LAN (local area network)                            | 局域网 (LAN)               |
| เครือข่ายอินเทอร์เน็ต                                                                     | Internet                                            | 互联网                     |
| เครื่องรับ, วงจร ภาครับ                                                                   | receiver                                            | 接收机 / 接收端               |
| เครื่องส่ง, วงจรภาคส่ง                                                                    | transmitter                                         | 发送机 / 发送端               |
| เครื่องหมายเข้าจังหวะ                                                                     | sync mark                                           | 同步标志                    |
| งานประ ยุกต์ (แอพลิเคชัน)                                                                 | application                                         | 应用                      |
| จาน, จานบันทึก                                                                            | disk                                                | 磁盘                      |
| จานบันทึกแม่เหล็ก                                                                         | magnetic disk                                       | 磁碟                      |
| จิตเตอร์                                                                                  | jitter                                              | 抖动                      |
| จิตเตอร์ทางเวลา                                                                           | timing jitter                                       | 定时抖动                    |
| จุดอิ่มตัว                                                                                | saturation point                                    | 饱和点                     |
| ช่องสัญญาณ                                                                                | channel                                             | 信道                      |
| ช่องสัญญาณสื่อสาร                                                                         | communication channel                               | 通信信道                    |
| ช่องสัญญาณอ่าน                                                                            | read channel                                        | 读取信道                    |
| ชิปช่องสัญญาณอ่าน                                                                         | read-channel chip                                   | 读取信道芯片                  |
| เชิงเส้น                                                                                  | linear                                              | 线性的                     |
| ซ้อนเหลื่อม                                                                               | overlap                                             | 重叠                      |
| ซูเปอร์พาราแมกเนติก                                                                       | superparamagnetic                                   | 超顺磁性                    |
| เซกเตอร์                                                                                  | sector                                              | 扇区                      |
| เซตย่อย                                                                                   | subset                                              | 子集                      |
| แซมเปิล (ตัวอย่าง)                                                                        | sample                                              | 样本                      |
| แซมเปิลที่ถูกแจงหน่วย                                                                     | quantized sample                                    | 量化样本                    |
| ไซนูซอยด์                                                                                 | sinusoidal                                          | 正弦的                     |
| ดิจิทัล                                                                                   | digital                                             | 数字                      |
| ดีแรม                                                                                     | DRAM (dynamic random access memory)                 | 动态随机访问存储器 (DRAM)        |
| เดซิเบล                                                                                   | dB (decibel)                                        | 分贝 (dB)                 |
| โดเมน                                                                                     | domain                                              | 域                       |
| โดเมน D                                                                                   | D domain                                            | D 域                     |
| โดเมน ZZ                                                                                  | ZZ domain                                           | Z 域                     |
| โดเมนความถี่                                                                              | frequency domain                                    | 频域                      |
| โดเมนที่ต่อเนื่องทางเวลา                                                                  | continuous-time domain                              | 连续时间域                   |
| โดเมนที่ไม่ต่อเนื่องทางเวลา                                                               | discrete-time domain                                | 离散时间域                   |
| โดเมนเวลา                                                                                 | time domain                                         | 时域                      |
| ตัวขับการเขียน                                                                            | write driver                                        | 写入驱动器                   |
| ตัวควบคุมการเคลื่อนไหว                                                                    | actuator                                            | 执行器                     |
| ตัวคูณร่วมน้อย                                                                            | least common multiple                               | 最小公倍数                   |
| ตัวชี้บอก                                                                                 | indicator                                           | 指示器                     |
| ตัวดำเนินการคอนโวลูชัน                                                                    | convolution operator                                | 卷积算子                    |
| ตัวดำเนินการค่าคาดหมาย                                                                    | expectation operator                                | 期望算子                    |
| ตัวดำเนินการหน่วงเวลา                                                                     | delay operator                                      | 延迟算子                    |
| ตัวไดรฟ์                                                                                  | drive                                               | 驱动器                     |
| ตัวประ กอบโร ลล์ออฟ                                                                       | roll-off factor                                     | 滚降因子                    |
| ตัวแปรสุ่ม                                                                                | random variable                                     | 随机变量                    |
| ตัวแปรสุ่มวิยุต                                                                           | discrete random variable                            | 离散随机变量                  |
| ตัวแปรสุมทวินาม                                                                           | binomial random variable                            | 二项随机变量                  |
| ตัวแปรสุ่มเบอร์นูลี                                                                       | bernoulli random variable                           | 伯努利随机变量                 |
| ตัวสไลเดอร์                                                                               | slider                                              | 滑块                      |
| ตารางค้นหา                                                                                | look-up table                                       | 查询表                     |
[11] A. M. Taratorin, Magnetic recording systems and measurements: Guzik Technical Enterprises, 2004.

[12] J. S. Goldberg, "Medium noise modeling, spinstand measurements, and timing recovery for magnetic recording," Ph.D. dissertation, Univ. Calif. San Diego, 2002.

[13] E. M. Kurtas, M. F. Erden, and X. Yang, "Future read chanel technologies and challenges for high density data storage applications," IEEE International Conference on Acoustics, Speech, and Signal Processing (ICAssP 2005), Philadelphia, USA, pp. v-737 – v-740, March 19 – 23, 2005.

[14] E. Grochowshi, Available online at http://www.hgst.com/hdd/technolo/overview/ chart08.html.

[15] R. L. White, "The physical boundaries to high-density magnetic recording," J. Magnetism and Magnetic Materials, vol. 209, no. 1, pp. 1 – 5, February 2000.

[16] Available online at http://db.usenix.org/events/fast02/coufal.pdf.

[17] E. Grochowshi, Available online at http://www.hgst.com/hdd/technolo/overview/ chart13.html.

[18] J. Moon, "The role of signal processing in data-storage," IEEE Signal Processing Magazine, pp. 54 – 72, July 1998.

[19] T. Suzuki, "Perpendicular magnetic recording: its basics and potential for the future," IEEE Trans. on Magnetics, vol. MAG-20, no. 5, pp. 675 – 680, September 1984.

[20] H. N. Bertram, Theory of magnetic recording. Cambridge: Cambridge University Press, 1994.

[21] M. .F. Erden, I. Ozgunes, and E. Kurtas, "Generalized transform filters in perpendicular recording architecture," Intermag Europe 2002, GP-01, April 28 – May 2, 2002.

[22] P. Kovintavewat, I. Ozgunes, E. Kurtas, J. R. Barry, and S. W. McLaughlin, "Generalized partial response targets for perpendicular recording with jitter noise," IEEE Trans. on Magnetics, vol. 38, no. 5, pp. 2340 – 2342, September 2002.

[23] J. M. Ruigrok, R. Coehoorn, S. R. Cumpson, and H. W. Kesteren, "Disk recording beyond 100 Gb/square inch: hybrid recording?," J. Applied Physics, vol. 87, no. 9, pp. 5398 – 5403, May 2000.

[24] T. W. McDaniel, W. A. Challener, and K. Sendur, "Issues in heat-assisted perpendicular recording," IEEE Trans. on Magnetics, vol. 39, no. 4, pp. 1972 – 1979, July 2003.

[25] H. F. Hamann, Y. C. Martin, and H. K. Wickramasinghe, "Thermally assisted recording beyond traditional limits," Applied Physics Letters, vol. 84, no. 5, pp. 810 – 812, 2004.

[26] H. J. Mamin, B. D. Terris, L. S. Fan, S. Hoen, R. C. Barrett, and D. Rugar, "High density data storage using proximal probe techniques," IBM Journal of Research and Development, vol. 39, no. 6, pp. 681 – 699, November 1995.

[27] L. R. Carley, G. Ganger, D. Guillou, and D. Nagle, "System design considerations for mems-actuated magnetic probe-based mass storage," IEEE Trans. on Magnetics, vol. 37, no. 3, pp. 657 – 662, 2001.

[28] Available online at http://www.research.ibm.com/journal/rd/443/ashley.html

[29] H. P. Hsu, Schaum's outline series: theory and problem of analog and digital communications. New York: McGraw-Hill, 1993

[30] Piya Kovintavewat, R CILAB 语言编程初学者手册 (第 2 版). 泰国国王科技学院 (KMUTNB) 教材生产中心, 2006.

[31] Available online at http://www.mathworks.com

[32] E. Ström, 'Notes of signals and systems," Available online at http://www. s2.chalmers.se/ undergraduate/courses/ess140/doc/Handouts.htm

[33] A. V. Oppenheim, A. S. Willsky, and S. H. Nawab, Signals and systems. New Jersey: Prentice Hall, 2nd-edition, 1997.

[34] Lanchakorn Wuthisithikulkit, 通信电学原理. 朱拉隆功大学出版社, 朱拉隆功大学, 2003.

[35] M. H. Hayes, Statistical digital signal processing and modeling. New York: John Wiley & Sons Inc., 1996.

[36] A. Leon-Garcia, Probability and random processes for electrical engineering. New York: Addison-Wesley Inc., 2nd-edition, 1994.

[37] J. R. Barry, E. A. Lee, and D. G. Messerschmitt, Digital communication. Boston: Kluwer Academic Publishers, 3nd-edition, 2003.

[38] J. G. Proakis, Digital communication. Singapore: McGraw Hill, 4th-edition, 2001.

[39] A. B. Carlson, P. B. Crilly, and J. C. Rutledge, Communication systems. Singapore: McGraw Hill, 4th-edition, 2002.

[40] Pornchai Subnithi, 数字通信系统. 泰国国王科技学院 (KMITL) 工程学院教材部门, 2006.

[41] C. E. Shannon, 'A mathematical theory of communication," The Bell system technical journal, vol. 27, pp. 379 – 423, 623 – 656, July, October, 1948.

[42] S. B. Wicker, Error control systems for digital communication and storage. New Jersey: Printice Hall International, 1995.

[43] B. Vasic and E. M. Kurtas, Coding and signal processing for magnetic recording systems. New York: CRC Press, 2005.

[44] K. A. S. Immink, "Runlength-limited sequences," in Proc. of the IEEE, vol. 78, no. 11, pp. 1745 – 1759, November 1990.

[45] A. R. Nayak, "Iterative timing recovery for magnetic recording channels with low signal-to-noise ratio," Ph.D. dissertation, Georgia Institute of Technology, Georgia, June 2004.

[46] R. Gallager, "Low-density parity-check codes," IRE Trans. Inform. Theory," vol. IT-8, pp. 21 – 28, January 1962.

[47] D. Raphaeli and Y. Zarai, "Combine turbo equalization and turbo decoding," in Proc. of Globecom'97, vol. 2, pp. 639 – 643, November 1997.

[48] A. Ghrayeb and W. E. Ryan, '"Precoder design for concatenating convolutional codes with generalized partial response channels," in Proc. of Globecom'00, San Francisco, CA, 2000, pp. 1859 – 1864.

[49] J. Caroselli and J. K. Wolf, "Error event characterization of partial response systems in magnetic recording systems with medium noise," in Proc. of Globecom'98, vol. 5, pp. 2724 - 2728.

[50] K. Senanan and R. H. Victora, Theoretical study of nonlinear transition shift in doublelayer perpendicular media," IEEE Trans. on Magnetics, vol. 38, no. 4, pp. 1664 – 1669, July 2002.

[51] H. Muraoka, R. Wood, and Y. Nakamura, "Nonlinear transition shift measurement in perpendicular magnetic recording," IEEE Trans. on Magnetics, vol. 32, no. 5, pp. 3926 – 3928, September 1996.

[52] Y. Lin and R. Wood, "An estimation technique for accurately modeling the magnetic recording channel including nonlinearities," IEEE Trans. on Magnetics, vol. MAG-25, no. 5, pp. 4058 – 4060, July 1989.

[53] Y. Tang and C. Tsang, "A technique for measuring nonlinear bit shift," IEEE Trans. on Magnetics, vol. 27, no. 6, pp. 5326 – 5328, November 1991.

[54] T A. Roscamp, E. D. Boerner, and G. J. Parker, "Three-dimensional modeling of perpendicular recording with soft underlayer," J. of Applied Physics, vol. 91, no. 10, May 2002.

[55] G. D. Forney, "Maximum-likelihood sequence estimation of digital sequences in the presence of intersymbol interference," IEEE Trans. on Information Theory, vol. IT-18, no. 3, pp. 363 – 378, May 1972.

[56] J. Moon and W. Zeng, Equalization for maximum likelihood detector," IEEE Trans. on Magnetics, vol. 31, no. 2, pp. 1083 – 1088, March 1995.

[57] D. G. Messerschmitt, "Design of finite impulse response for the Viterbi algorithm and decision-feedback equalizer," in Proc. of I.C.C., pp. 37D-1-5, June 1974.

[58] J. Fitzpatrick, J. K. Wolf, and L. Barbosa, "New equalizer targets for sampled magnetic recording system," in Proc. of the 25th Asilomar Conference on Signals Systems and Computers, pp. 30 – 34, November 1991.

[59] H. K. Thapar and A. M. Patel, "A class of partial response systems for increasing storage density in magnetic recording," IEEE Trans. on Magnetics, vol. 23, no. 5, pp 3666 – 3668, September 1987.
