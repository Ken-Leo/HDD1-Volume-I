## ตารางฟังก์ชั้น Q

ฟังก์ชัน $Q ( x )$ เป็นฟังก์ชันที่สามารถจัดให้อยู่ในรูปของฟังก์ชันการแจกแจงสะสมของตัวแปรสุ่มแบบ เกาส์เซียนได้ซึ่งเป็นที่นิยมใช้งานทางด้านสถิติศาสตร์และด้านวิศวกรรมศาสตร์ โดยฟังก์ชัน $Q ( x )$ จะ

$$
Q ( x ) = { \frac { 1 } { \sqrt { 2 \pi } } } \int _ { x } ^ { \infty } \exp \left\{ - { \frac { y ^ { 2 } } { 2 } } \right\} d y\tag{ก.1}
$$

ซึ่งเป็นการหาค่าปริพันธ์ส่วนหางของฟังก์ชันความหนาแน่นความน่าจะเป็นแบบเกาส์เซียนเมื่อ exp[+] คือ ฟังก์ชันเลขชี้กำลัง (exponential function) โดยทั่วไป ค่าของฟังก์ชัน $Q ( x )$ สำหรับค่า x ต่างๆ สามารถหาได้จากตารางค้นหา (10ok-up table) แต่ในกรณีที่ $x \gg 3$ ฟังก์ชัน $Q ( x )$ สามารถประมาณ ค่าได้ดังนี้

$$
Q ( x ) \approx \frac { 1 } { x \sqrt { 2 \pi } } \exp \left\{ - \frac { x ^ { 2 } } { 2 } \right\}\tag{ก.2}
$$

ตารางต่อไปนี้จะแสดงค่าของฟังก์ชัน $Q ( x )$ สำหรับ $0 \leq x \leq 3 . 5 9$

<table><tr><td colspan="1" rowspan="1">x</td><td colspan="1" rowspan="1">Q(x)</td><td colspan="1" rowspan="1">x</td><td colspan="1" rowspan="1">Q(x)</td><td colspan="1" rowspan="1">x</td><td colspan="1" rowspan="1">Q(x)</td><td colspan="1" rowspan="1">x</td><td colspan="1" rowspan="1">Q (x)</td><td colspan="1" rowspan="1">x</td><td colspan="1" rowspan="1">Q(x)</td></tr><tr><td colspan="1" rowspan="1">0</td><td colspan="1" rowspan="1">0.50000</td><td colspan="1" rowspan="1">0.36</td><td colspan="1" rowspan="1">0.35942</td><td colspan="1" rowspan="1">0.72</td><td colspan="1" rowspan="1">0.23576</td><td colspan="1" rowspan="1">1.08</td><td colspan="1" rowspan="1">0.14007</td><td colspan="1" rowspan="1">1.44</td><td colspan="1" rowspan="1">0.0749340</td></tr><tr><td colspan="1" rowspan="1">0.01</td><td colspan="1" rowspan="1">0.49601</td><td colspan="1" rowspan="1">0.37</td><td colspan="1" rowspan="1">0.35569</td><td colspan="1" rowspan="1">0.73</td><td colspan="1" rowspan="1">0.23270</td><td colspan="1" rowspan="1">1.09</td><td colspan="1" rowspan="1">0.13786</td><td colspan="1" rowspan="1">1.45</td><td colspan="1" rowspan="1">0.0735290</td></tr><tr><td colspan="1" rowspan="1">0.02</td><td colspan="1" rowspan="1">0.49202</td><td colspan="1" rowspan="1">0.38</td><td colspan="1" rowspan="1">0.35197</td><td colspan="1" rowspan="1">0.74</td><td colspan="1" rowspan="1">0.22965</td><td colspan="1" rowspan="1">1.10</td><td colspan="1" rowspan="1">0.13567</td><td colspan="1" rowspan="1">1.46</td><td colspan="1" rowspan="1">0.0721450</td></tr><tr><td colspan="1" rowspan="1">0.03</td><td colspan="1" rowspan="1">0.48803</td><td colspan="1" rowspan="1">0.39</td><td colspan="1" rowspan="1">0.34827</td><td colspan="1" rowspan="1">0.75</td><td colspan="1" rowspan="1">0.22663</td><td colspan="1" rowspan="1">1.11</td><td colspan="1" rowspan="1">0.133500</td><td colspan="1" rowspan="1">1.47</td><td colspan="1" rowspan="1">0.070781</td></tr><tr><td colspan="1" rowspan="1">0.04</td><td colspan="1" rowspan="1">0.48405</td><td colspan="1" rowspan="1">0.40</td><td colspan="1" rowspan="1">0.34458</td><td colspan="1" rowspan="1">0.76</td><td colspan="1" rowspan="1">0.22363</td><td colspan="1" rowspan="1">1.12</td><td colspan="1" rowspan="1">0.131360</td><td colspan="1" rowspan="1">1.48</td><td colspan="1" rowspan="1">0.069437</td></tr><tr><td colspan="1" rowspan="1">0.05</td><td colspan="1" rowspan="1">0.48006</td><td colspan="1" rowspan="1">0.41</td><td colspan="1" rowspan="1">0.34090</td><td colspan="1" rowspan="1">0.77</td><td colspan="1" rowspan="1">0.22065</td><td colspan="1" rowspan="1">1.13</td><td colspan="1" rowspan="1">0.129240</td><td colspan="1" rowspan="1">1.49</td><td colspan="1" rowspan="1">0.068112</td></tr><tr><td colspan="1" rowspan="1">0.06</td><td colspan="1" rowspan="1">0.47608</td><td colspan="1" rowspan="1">0.42</td><td colspan="1" rowspan="1">0.33724</td><td colspan="1" rowspan="1">0.78</td><td colspan="1" rowspan="1">0.21770</td><td colspan="1" rowspan="1">1.14</td><td colspan="1" rowspan="1">0.127140</td><td colspan="1" rowspan="1">1.50</td><td colspan="1" rowspan="1">0.066807</td></tr><tr><td colspan="1" rowspan="1">0.07</td><td colspan="1" rowspan="1">0.47210</td><td colspan="1" rowspan="1">0.43</td><td colspan="1" rowspan="1">0.33360</td><td colspan="1" rowspan="1">0.79</td><td colspan="1" rowspan="1">0.21476</td><td colspan="1" rowspan="1">1.15</td><td colspan="1" rowspan="1">0.125070</td><td colspan="1" rowspan="1">1.51</td><td colspan="1" rowspan="1">0.065522</td></tr><tr><td colspan="1" rowspan="1">0.08</td><td colspan="1" rowspan="1">0.46812</td><td colspan="1" rowspan="1">0.44</td><td colspan="1" rowspan="1">0.32997</td><td colspan="1" rowspan="1">0.80</td><td colspan="1" rowspan="1">0.21186</td><td colspan="1" rowspan="1">1.16</td><td colspan="1" rowspan="1">0.123020</td><td colspan="1" rowspan="1">1.52</td><td colspan="1" rowspan="1">0.064255</td></tr><tr><td colspan="1" rowspan="1">0.09</td><td colspan="1" rowspan="1">0.46414</td><td colspan="1" rowspan="1">0.45</td><td colspan="1" rowspan="1">0.32636</td><td colspan="1" rowspan="1">0.81</td><td colspan="1" rowspan="1">0.20897</td><td colspan="1" rowspan="1">1.17</td><td colspan="1" rowspan="1">0.121000</td><td colspan="1" rowspan="1">1.53</td><td colspan="1" rowspan="1">0.063008</td></tr><tr><td colspan="1" rowspan="1">0.10</td><td colspan="1" rowspan="1">0.46017</td><td colspan="1" rowspan="1">0.46</td><td colspan="1" rowspan="1">0.32276</td><td colspan="1" rowspan="1">0.82</td><td colspan="1" rowspan="1">0.20611</td><td colspan="1" rowspan="1">1.18</td><td colspan="1" rowspan="1">0.119000</td><td colspan="1" rowspan="1">1.54</td><td colspan="1" rowspan="1">0.061780</td></tr><tr><td colspan="1" rowspan="1">0.11</td><td colspan="1" rowspan="1">0.45620</td><td colspan="1" rowspan="1">0.47</td><td colspan="1" rowspan="1">0.31918</td><td colspan="1" rowspan="1">0.83</td><td colspan="1" rowspan="1">0.20327</td><td colspan="1" rowspan="1">1.19</td><td colspan="1" rowspan="1">0.117020</td><td colspan="1" rowspan="1">1.55</td><td colspan="1" rowspan="1">0.060571</td></tr><tr><td colspan="1" rowspan="1">0.12</td><td colspan="1" rowspan="1">0.45224</td><td colspan="1" rowspan="1">0.48</td><td colspan="1" rowspan="1">0.31561</td><td colspan="1" rowspan="1">0.84</td><td colspan="1" rowspan="1">0.20045</td><td colspan="1" rowspan="1">1.20</td><td colspan="1" rowspan="1">0.115070</td><td colspan="1" rowspan="1">1.56</td><td colspan="1" rowspan="1">0.059380</td></tr><tr><td colspan="1" rowspan="1">0.13</td><td colspan="1" rowspan="1">0.44828</td><td colspan="1" rowspan="1">0.49</td><td colspan="1" rowspan="1">0.31207</td><td colspan="1" rowspan="1">0.85</td><td colspan="1" rowspan="1">0.19766</td><td colspan="1" rowspan="1">1.21</td><td colspan="1" rowspan="1">0.113140</td><td colspan="1" rowspan="1">1.57</td><td colspan="1" rowspan="1">0.058208</td></tr><tr><td colspan="1" rowspan="1">0.14</td><td colspan="1" rowspan="1">0.44433</td><td colspan="1" rowspan="1">0.50</td><td colspan="1" rowspan="1">0.30854</td><td colspan="1" rowspan="1">0.86</td><td colspan="1" rowspan="1">0.19489</td><td colspan="1" rowspan="1">1.22</td><td colspan="1" rowspan="1">0.111230</td><td colspan="1" rowspan="1">1.58</td><td colspan="1" rowspan="1">0.057053</td></tr><tr><td colspan="1" rowspan="1">0.15</td><td colspan="1" rowspan="1">0.44038</td><td colspan="1" rowspan="1">0.51</td><td colspan="1" rowspan="1">0.30503</td><td colspan="1" rowspan="1">0.87</td><td colspan="1" rowspan="1">0.19215</td><td colspan="1" rowspan="1">1.23</td><td colspan="1" rowspan="1">0.109350</td><td colspan="1" rowspan="1">1.59</td><td colspan="1" rowspan="1">0.055917</td></tr><tr><td colspan="1" rowspan="1">0.16</td><td colspan="1" rowspan="1">0.43644</td><td colspan="1" rowspan="1">0.52</td><td colspan="1" rowspan="1">0.30153</td><td colspan="1" rowspan="1">0.88</td><td colspan="1" rowspan="1">0.18943</td><td colspan="1" rowspan="1">1.24</td><td colspan="1" rowspan="1">0.107490</td><td colspan="1" rowspan="1">1.60</td><td colspan="1" rowspan="1">0.054799</td></tr><tr><td colspan="1" rowspan="1">0.17</td><td colspan="1" rowspan="1">0.43251</td><td colspan="1" rowspan="1">0.53</td><td colspan="1" rowspan="1">0.29806</td><td colspan="1" rowspan="1">0.89</td><td colspan="1" rowspan="1">0.18673</td><td colspan="1" rowspan="1">1.25</td><td colspan="1" rowspan="1">0.105650</td><td colspan="1" rowspan="1">1.61</td><td colspan="1" rowspan="1">0.053699</td></tr><tr><td colspan="1" rowspan="1">0.18</td><td colspan="1" rowspan="1">0.42858</td><td colspan="1" rowspan="1">0.54</td><td colspan="1" rowspan="1">0.29460</td><td colspan="1" rowspan="1">0.90</td><td colspan="1" rowspan="1">0.18406</td><td colspan="1" rowspan="1">1.26</td><td colspan="1" rowspan="1">0.103830</td><td colspan="1" rowspan="1">1.62</td><td colspan="1" rowspan="1">0.052616</td></tr><tr><td colspan="1" rowspan="1">0.19</td><td colspan="1" rowspan="1">0.42465</td><td colspan="1" rowspan="1">0.55</td><td colspan="1" rowspan="1">0.29116</td><td colspan="1" rowspan="1">0.91</td><td colspan="1" rowspan="1">0.18141</td><td colspan="1" rowspan="1">1.27</td><td colspan="1" rowspan="1">0.102040</td><td colspan="1" rowspan="1">1.63</td><td colspan="1" rowspan="1">0.051551</td></tr><tr><td colspan="1" rowspan="1">0.20</td><td colspan="1" rowspan="1">0.42074</td><td colspan="1" rowspan="1">0.56</td><td colspan="1" rowspan="1">0.28774</td><td colspan="1" rowspan="1">0.92</td><td colspan="1" rowspan="1">0.17879</td><td colspan="1" rowspan="1">1.28</td><td colspan="1" rowspan="1">0.100270</td><td colspan="1" rowspan="1">1.64</td><td colspan="1" rowspan="1">0.050503</td></tr><tr><td colspan="1" rowspan="1">0.21</td><td colspan="1" rowspan="1">0.41683</td><td colspan="1" rowspan="1">0.57</td><td colspan="1" rowspan="1">0.28434</td><td colspan="1" rowspan="1">0.93</td><td colspan="1" rowspan="1">0.17619</td><td colspan="1" rowspan="1">1.29</td><td colspan="1" rowspan="1">0.098525</td><td colspan="1" rowspan="1">1.65</td><td colspan="1" rowspan="1">0.049471</td></tr><tr><td colspan="1" rowspan="1">0.22</td><td colspan="1" rowspan="1">0.41294</td><td colspan="1" rowspan="1">0.58</td><td colspan="1" rowspan="1">0.28096</td><td colspan="1" rowspan="1">0.94</td><td colspan="1" rowspan="1">0.17361</td><td colspan="1" rowspan="1">1.30</td><td colspan="1" rowspan="1">0.096800</td><td colspan="1" rowspan="1">1.66</td><td colspan="1" rowspan="1">0.048457</td></tr><tr><td colspan="1" rowspan="1">0.23</td><td colspan="1" rowspan="1">0.40905</td><td colspan="1" rowspan="1">0.59</td><td colspan="1" rowspan="1">0.27760</td><td colspan="1" rowspan="1">0.95</td><td colspan="1" rowspan="1">0.17106</td><td colspan="1" rowspan="1">1.31</td><td colspan="1" rowspan="1">0.095098</td><td colspan="1" rowspan="1">1.67</td><td colspan="1" rowspan="1">0.047460</td></tr><tr><td colspan="1" rowspan="1">0.24</td><td colspan="1" rowspan="1">0.40517</td><td colspan="1" rowspan="1">0.60</td><td colspan="1" rowspan="1">0.27425</td><td colspan="1" rowspan="1">0.96</td><td colspan="1" rowspan="1">0.16853</td><td colspan="1" rowspan="1">1.32</td><td colspan="1" rowspan="1">0.093418</td><td colspan="1" rowspan="1">1.68</td><td colspan="1" rowspan="1">0.046479</td></tr><tr><td colspan="1" rowspan="1">0.25</td><td colspan="1" rowspan="1">0.40129</td><td colspan="1" rowspan="1">0.61</td><td colspan="1" rowspan="1">0.27093</td><td colspan="1" rowspan="1">0.97</td><td colspan="1" rowspan="1">0.16602</td><td colspan="1" rowspan="1">1.33</td><td colspan="1" rowspan="1">0.091759</td><td colspan="1" rowspan="1">1.69</td><td colspan="1" rowspan="1">0.045514</td></tr><tr><td colspan="1" rowspan="1">0.26</td><td colspan="1" rowspan="1">0.39743</td><td colspan="1" rowspan="1">0.62</td><td colspan="1" rowspan="1">0.26763</td><td colspan="1" rowspan="1">0.98</td><td colspan="1" rowspan="1">0.16354</td><td colspan="1" rowspan="1">1.34</td><td colspan="1" rowspan="1">0.090123</td><td colspan="1" rowspan="1">1.70</td><td colspan="1" rowspan="1">0.044565</td></tr><tr><td colspan="1" rowspan="1">0.27</td><td colspan="1" rowspan="1">0.39358</td><td colspan="1" rowspan="1">0.63</td><td colspan="1" rowspan="1">0.26435</td><td colspan="1" rowspan="1">0.99</td><td colspan="1" rowspan="1">0.16109</td><td colspan="1" rowspan="1">1.35</td><td colspan="1" rowspan="1">0.088508</td><td colspan="1" rowspan="1">1.71</td><td colspan="1" rowspan="1">0.043633</td></tr><tr><td colspan="1" rowspan="1">0.28</td><td colspan="1" rowspan="1">0.38974</td><td colspan="1" rowspan="1">0.64</td><td colspan="1" rowspan="1">0.26109</td><td colspan="1" rowspan="1">1.00</td><td colspan="1" rowspan="1">0.15866</td><td colspan="1" rowspan="1">1.36</td><td colspan="1" rowspan="1">0.086915</td><td colspan="1" rowspan="1">1.72</td><td colspan="1" rowspan="1">0.042716</td></tr><tr><td colspan="1" rowspan="1">0.29</td><td colspan="1" rowspan="1">0.38591</td><td colspan="1" rowspan="1">0.65</td><td colspan="1" rowspan="1">0.25785</td><td colspan="1" rowspan="1">1.01</td><td colspan="1" rowspan="1">0.15625</td><td colspan="1" rowspan="1">1.37</td><td colspan="1" rowspan="1">0.085343</td><td colspan="1" rowspan="1">1.73</td><td colspan="1" rowspan="1">0.041815</td></tr><tr><td colspan="1" rowspan="1">0.30</td><td colspan="1" rowspan="1">0.38209</td><td colspan="1" rowspan="1">0.66</td><td colspan="1" rowspan="1">0.25463</td><td colspan="1" rowspan="1">1.02</td><td colspan="1" rowspan="1">0.15386</td><td colspan="1" rowspan="1">1.38</td><td colspan="1" rowspan="1">0.083793</td><td colspan="1" rowspan="1">1.74</td><td colspan="1" rowspan="1">0.040930</td></tr><tr><td colspan="1" rowspan="1">0.31</td><td colspan="1" rowspan="1">0.37828</td><td colspan="1" rowspan="1">0.67</td><td colspan="1" rowspan="1">0.25143</td><td colspan="1" rowspan="1">1.03</td><td colspan="1" rowspan="1">0.15151</td><td colspan="1" rowspan="1">1.39</td><td colspan="1" rowspan="1">0.082264</td><td colspan="1" rowspan="1">1.75</td><td colspan="1" rowspan="1">0.040059</td></tr><tr><td colspan="1" rowspan="1">0.32</td><td colspan="1" rowspan="1">0.37448</td><td colspan="1" rowspan="1">0.68</td><td colspan="1" rowspan="1">0.24825</td><td colspan="1" rowspan="1">1.04</td><td colspan="1" rowspan="1">0.14917</td><td colspan="1" rowspan="1">1.40</td><td colspan="1" rowspan="1">0.080757</td><td colspan="1" rowspan="1">1.76</td><td colspan="1" rowspan="1">0.039204</td></tr><tr><td colspan="1" rowspan="1">0.33</td><td colspan="1" rowspan="1">0.37070</td><td colspan="1" rowspan="1">0.69</td><td colspan="1" rowspan="1">0.24510</td><td colspan="1" rowspan="1">1.05</td><td colspan="1" rowspan="1">0.14686</td><td colspan="1" rowspan="1">1.41</td><td colspan="1" rowspan="1">0.079270</td><td colspan="1" rowspan="1">1.77</td><td colspan="1" rowspan="1">0.038364</td></tr><tr><td colspan="1" rowspan="1">0.34</td><td colspan="1" rowspan="1">0.36693</td><td colspan="1" rowspan="1">0.70</td><td colspan="1" rowspan="1">0.24196</td><td colspan="1" rowspan="1">1.06</td><td colspan="1" rowspan="1">0.14457</td><td colspan="1" rowspan="1">1.42</td><td colspan="1" rowspan="1">0.077804</td><td colspan="1" rowspan="1">1.78</td><td colspan="1" rowspan="1">0.037538</td></tr><tr><td colspan="1" rowspan="1">0.35</td><td colspan="1" rowspan="1">0.36317</td><td colspan="1" rowspan="1">0.71</td><td colspan="1" rowspan="1">0.23885</td><td colspan="1" rowspan="1">1.07</td><td colspan="1" rowspan="1">0.14231</td><td colspan="1" rowspan="1">1.43</td><td colspan="1" rowspan="1">0.076359</td><td colspan="1" rowspan="1">1.79</td><td colspan="1" rowspan="1">0.036727</td></tr><tr><td colspan="1" rowspan="1">1.80</td><td colspan="1" rowspan="1">0.035930</td><td colspan="1" rowspan="1">2.16</td><td colspan="1" rowspan="1">0.0153860</td><td colspan="1" rowspan="1">2.52</td><td colspan="1" rowspan="1">0.0058677</td><td colspan="1" rowspan="1">2.88</td><td colspan="1" rowspan="1">0.00198840</td><td colspan="1" rowspan="1">3.24</td><td colspan="1" rowspan="1">0.00059765</td></tr><tr><td colspan="1" rowspan="1">1.81</td><td colspan="1" rowspan="1">0.035148</td><td colspan="1" rowspan="1">2.17</td><td colspan="1" rowspan="1">0.0150030</td><td colspan="1" rowspan="1">2.53</td><td colspan="1" rowspan="1">0.0057031</td><td colspan="1" rowspan="1">2.89</td><td colspan="1" rowspan="1">0.00192620</td><td colspan="1" rowspan="1">3.25</td><td colspan="1" rowspan="1">0.00057703</td></tr><tr><td colspan="1" rowspan="1">1.82</td><td colspan="1" rowspan="1">0.034380</td><td colspan="1" rowspan="1">2.18</td><td colspan="1" rowspan="1">0.0146290</td><td colspan="1" rowspan="1">2.54</td><td colspan="1" rowspan="1">0.0055426</td><td colspan="1" rowspan="1">2.90</td><td colspan="1" rowspan="1">0.00186580</td><td colspan="1" rowspan="1">3.26</td><td colspan="1" rowspan="2">0.000557060.00053774</td></tr><tr><td colspan="1" rowspan="1">1.83</td><td colspan="1" rowspan="1">0.033625</td><td colspan="1" rowspan="1">2.19</td><td colspan="1" rowspan="1">0.0142620</td><td colspan="1" rowspan="1">2.55</td><td colspan="1" rowspan="1">0.0053861</td><td colspan="1" rowspan="1">2.91</td><td colspan="1" rowspan="1">0.00180710</td><td colspan="1" rowspan="1">3.27</td></tr><tr><td colspan="1" rowspan="1">1.84</td><td colspan="1" rowspan="1">0.032884</td><td colspan="1" rowspan="1">2.20</td><td colspan="1" rowspan="1">0.0139030</td><td colspan="1" rowspan="1">2.56</td><td colspan="1" rowspan="1">0.0052336</td><td colspan="1" rowspan="1">2.92</td><td colspan="1" rowspan="1">0.00175020</td><td colspan="1" rowspan="1">3.28</td><td colspan="1" rowspan="1">0.00051904</td></tr><tr><td colspan="1" rowspan="1">1.85</td><td colspan="1" rowspan="1">0.032157</td><td colspan="1" rowspan="1">2.21</td><td colspan="1" rowspan="1">0.0135530</td><td colspan="1" rowspan="1">2.57</td><td colspan="1" rowspan="1">0.0050849</td><td colspan="1" rowspan="1">2.93</td><td colspan="1" rowspan="1">0.00169480</td><td colspan="1" rowspan="2">3.293.30</td><td colspan="1" rowspan="2">0.000500940.00048342</td></tr><tr><td colspan="1" rowspan="1">1.86</td><td colspan="1" rowspan="1">0.031443</td><td colspan="1" rowspan="1">2.22</td><td colspan="1" rowspan="1">0.0132090</td><td colspan="1" rowspan="1">2.58</td><td colspan="1" rowspan="1">0.0049400</td><td colspan="1" rowspan="1">2.94</td><td colspan="1" rowspan="1">0.00164110</td></tr><tr><td colspan="1" rowspan="1">1.87</td><td colspan="1" rowspan="1">0.030742</td><td colspan="1" rowspan="1">2.23</td><td colspan="1" rowspan="1">0.0128740</td><td colspan="1" rowspan="1">2.59</td><td colspan="1" rowspan="1">0.0047988</td><td colspan="1" rowspan="1">2.95</td><td colspan="1" rowspan="1">0.00158890</td><td colspan="1" rowspan="1">3.31</td><td colspan="1" rowspan="2">0.000466480.00045009</td></tr><tr><td colspan="1" rowspan="1">1.88</td><td colspan="1" rowspan="1">0.030054</td><td colspan="1" rowspan="1">2.24</td><td colspan="1" rowspan="1">0.0125450</td><td colspan="1" rowspan="1">2.60</td><td colspan="1" rowspan="1">0.0046612</td><td colspan="1" rowspan="1">2.96</td><td colspan="1" rowspan="1">0.00153820</td><td colspan="1" rowspan="1">3.32</td></tr><tr><td colspan="1" rowspan="1">1.89</td><td colspan="1" rowspan="1">0.029379</td><td colspan="1" rowspan="1">2.25</td><td colspan="1" rowspan="1">0.0122240</td><td colspan="1" rowspan="1">2.61</td><td colspan="1" rowspan="1">0.0045271</td><td colspan="1" rowspan="1">2.97</td><td colspan="1" rowspan="1">0.00148900</td><td colspan="1" rowspan="1">3.33</td><td colspan="1" rowspan="1">0.00043423</td></tr><tr><td colspan="1" rowspan="1">1.90</td><td colspan="1" rowspan="1">0.028717</td><td colspan="1" rowspan="1">2.26</td><td colspan="1" rowspan="1">0.0119110</td><td colspan="1" rowspan="1">2.62</td><td colspan="1" rowspan="1">0.0043965</td><td colspan="1" rowspan="1">2.98</td><td colspan="1" rowspan="1">0.00144120</td><td colspan="1" rowspan="1">3.34</td><td colspan="1" rowspan="1">0.00041889</td></tr><tr><td colspan="1" rowspan="1">1.91</td><td colspan="1" rowspan="1">0.028067</td><td colspan="1" rowspan="1">2.27</td><td colspan="1" rowspan="1">0.0116040</td><td colspan="1" rowspan="1">2.63</td><td colspan="1" rowspan="1">0.0042692</td><td colspan="1" rowspan="1">2.99</td><td colspan="1" rowspan="1">0.00139490</td><td colspan="1" rowspan="1">3.35</td><td colspan="1" rowspan="1">0.00040406</td></tr><tr><td colspan="1" rowspan="1">1.92</td><td colspan="1" rowspan="1">0.027429</td><td colspan="1" rowspan="1">2.28</td><td colspan="1" rowspan="1">0.0113040</td><td colspan="1" rowspan="1">2.64</td><td colspan="1" rowspan="1">0.0041453</td><td colspan="1" rowspan="1">3.00</td><td colspan="1" rowspan="1">0.00134990</td><td colspan="1" rowspan="1">3.36</td><td colspan="1" rowspan="1">0.00038971</td></tr><tr><td colspan="1" rowspan="1">1.93</td><td colspan="1" rowspan="1">0.026803</td><td colspan="1" rowspan="1">2.29</td><td colspan="1" rowspan="1">0.0110110</td><td colspan="1" rowspan="1">2.65</td><td colspan="1" rowspan="1">0.0040246</td><td colspan="1" rowspan="1">3.01</td><td colspan="1" rowspan="1">0.00130620</td><td colspan="1" rowspan="1">3.37</td><td colspan="1" rowspan="1">0.00037584</td></tr><tr><td colspan="1" rowspan="1">1.94</td><td colspan="1" rowspan="1">0.026190</td><td colspan="1" rowspan="1">2.30</td><td colspan="1" rowspan="1">0.0107240</td><td colspan="1" rowspan="1">2.66</td><td colspan="1" rowspan="1">0.0039070</td><td colspan="1" rowspan="1">3.02</td><td colspan="1" rowspan="1">0.00126390</td><td colspan="1" rowspan="1">3.38</td><td colspan="1" rowspan="1">0.00036243</td></tr><tr><td colspan="1" rowspan="1">1.95</td><td colspan="1" rowspan="1">0.025588</td><td colspan="1" rowspan="1">2.31</td><td colspan="1" rowspan="1">0.0104440</td><td colspan="1" rowspan="1">2.67</td><td colspan="1" rowspan="1">0.0037926</td><td colspan="1" rowspan="1">3.03</td><td colspan="1" rowspan="1">0.00122280</td><td colspan="1" rowspan="1">3.39</td><td colspan="1" rowspan="1">0.00034946</td></tr><tr><td colspan="1" rowspan="1">1.96</td><td colspan="1" rowspan="1">0.024998</td><td colspan="1" rowspan="1">2.32</td><td colspan="1" rowspan="1">0.0101700</td><td colspan="1" rowspan="1">2.68</td><td colspan="1" rowspan="1">0.0036811</td><td colspan="1" rowspan="1">3.04</td><td colspan="1" rowspan="1">0.00118290</td><td colspan="1" rowspan="1">3.40</td><td colspan="1" rowspan="1">0.00033693</td></tr><tr><td colspan="1" rowspan="1">1.97</td><td colspan="1" rowspan="1">0.024419</td><td colspan="1" rowspan="1">2.33</td><td colspan="1" rowspan="1">0.0099031</td><td colspan="1" rowspan="1">2.69</td><td colspan="1" rowspan="1">0.0035726</td><td colspan="1" rowspan="1">3.05</td><td colspan="1" rowspan="1">0.00114420</td><td colspan="1" rowspan="1">3.41</td><td colspan="1" rowspan="1">0.00032481</td></tr><tr><td colspan="1" rowspan="1">1.98</td><td colspan="1" rowspan="1">0.023852</td><td colspan="1" rowspan="1">2.34</td><td colspan="1" rowspan="1">0.0096419</td><td colspan="1" rowspan="1">2.70</td><td colspan="1" rowspan="1">0.0034670</td><td colspan="1" rowspan="1">3.06</td><td colspan="1" rowspan="1">0.00110670</td><td colspan="1" rowspan="1">3.42</td><td colspan="1" rowspan="1">0.00031311</td></tr><tr><td colspan="1" rowspan="1">1.99</td><td colspan="1" rowspan="1">0.023295</td><td colspan="1" rowspan="1">2.35</td><td colspan="1" rowspan="1">0.0093867</td><td colspan="1" rowspan="1">2.71</td><td colspan="1" rowspan="1">0.0033642</td><td colspan="1" rowspan="1">3.07</td><td colspan="1" rowspan="1">0.00107030</td><td colspan="1" rowspan="1">3.43</td><td colspan="1" rowspan="1">0.00030179</td></tr><tr><td colspan="1" rowspan="1">2.00</td><td colspan="1" rowspan="1">0.022750</td><td colspan="1" rowspan="1">2.36</td><td colspan="1" rowspan="1">0.0091375</td><td colspan="1" rowspan="1">2.72</td><td colspan="1" rowspan="1">0.0032641</td><td colspan="1" rowspan="1">3.08</td><td colspan="1" rowspan="1">0.00103500</td><td colspan="1" rowspan="1">3.44</td><td colspan="1" rowspan="1">0.00029086</td></tr><tr><td colspan="1" rowspan="1">2.01</td><td colspan="1" rowspan="1">0.022216</td><td colspan="1" rowspan="1">2.37</td><td colspan="1" rowspan="1">0.0088940</td><td colspan="1" rowspan="1">2.73</td><td colspan="1" rowspan="1">0.0031667</td><td colspan="1" rowspan="1">3.09</td><td colspan="1" rowspan="1">0.00100080</td><td colspan="1" rowspan="1">3.45</td><td colspan="1" rowspan="1">0.00028029</td></tr><tr><td colspan="1" rowspan="1">2.02</td><td colspan="1" rowspan="1">0.021692</td><td colspan="1" rowspan="1">2.38</td><td colspan="1" rowspan="1">0.0086563</td><td colspan="1" rowspan="1">2.74</td><td colspan="1" rowspan="1">0.0030720</td><td colspan="1" rowspan="1">3.10</td><td colspan="1" rowspan="1">0.00096760</td><td colspan="1" rowspan="1">3.46</td><td colspan="1" rowspan="1">0.00027009</td></tr><tr><td colspan="1" rowspan="1">2.03</td><td colspan="1" rowspan="1">0.021178</td><td colspan="1" rowspan="1">2.39</td><td colspan="1" rowspan="1">0.0084242</td><td colspan="1" rowspan="1">2.75</td><td colspan="1" rowspan="1">0.0029798</td><td colspan="1" rowspan="1">3.11</td><td colspan="1" rowspan="1">0.00093544</td><td colspan="1" rowspan="1">3.47</td><td colspan="1" rowspan="1">0.00026023</td></tr><tr><td colspan="1" rowspan="1">2.04</td><td colspan="1" rowspan="1">0.020675</td><td colspan="1" rowspan="1">2.40</td><td colspan="1" rowspan="1">0.0081975</td><td colspan="1" rowspan="1">2.76</td><td colspan="1" rowspan="1">0.0028901</td><td colspan="1" rowspan="1">3.12</td><td colspan="1" rowspan="1">0.00090426</td><td colspan="1" rowspan="1">3.48</td><td colspan="1" rowspan="1">0.00025071</td></tr><tr><td colspan="1" rowspan="1">2.05</td><td colspan="1" rowspan="1">0.020182</td><td colspan="1" rowspan="1">2.41</td><td colspan="1" rowspan="1">0.0079763</td><td colspan="1" rowspan="1">2.77</td><td colspan="1" rowspan="1">0.0028028</td><td colspan="1" rowspan="1">3.13</td><td colspan="1" rowspan="1">0.00087403</td><td colspan="1" rowspan="1">3.49</td><td colspan="1" rowspan="1">0.00024151</td></tr><tr><td colspan="1" rowspan="1">2.06</td><td colspan="1" rowspan="1">0.019699</td><td colspan="1" rowspan="1">2.42</td><td colspan="1" rowspan="1">0.0077603</td><td colspan="1" rowspan="1">2.78</td><td colspan="1" rowspan="1">0.0027179</td><td colspan="1" rowspan="1">3.14</td><td colspan="1" rowspan="1">0.00084474</td><td colspan="1" rowspan="1">3.50</td><td colspan="1" rowspan="1">0.00023263</td></tr><tr><td colspan="1" rowspan="1">2.07</td><td colspan="1" rowspan="1">0.019226</td><td colspan="1" rowspan="1">2.43</td><td colspan="1" rowspan="1">0.0075494</td><td colspan="1" rowspan="1">2.79</td><td colspan="1" rowspan="1">0.0026354</td><td colspan="1" rowspan="1">3.15</td><td colspan="1" rowspan="1">0.00081635</td><td colspan="1" rowspan="1">3.51</td><td colspan="1" rowspan="1">0.00022405</td></tr><tr><td colspan="1" rowspan="1">2.08</td><td colspan="1" rowspan="1">0.018763</td><td colspan="1" rowspan="1">2.44</td><td colspan="1" rowspan="1">0.0073436</td><td colspan="1" rowspan="1">2.80</td><td colspan="1" rowspan="1">0.0025551</td><td colspan="1" rowspan="1">3.16</td><td colspan="1" rowspan="1">0.00078885</td><td colspan="1" rowspan="1">3.52</td><td colspan="1" rowspan="1">0.00021577</td></tr><tr><td colspan="1" rowspan="1">2.09</td><td colspan="1" rowspan="1">0.018309</td><td colspan="1" rowspan="1">2.45</td><td colspan="1" rowspan="1">0.0071428</td><td colspan="1" rowspan="1">2.81</td><td colspan="1" rowspan="1">0.0024771</td><td colspan="1" rowspan="1">3.17</td><td colspan="1" rowspan="1">0.00076219</td><td colspan="1" rowspan="1">3.53</td><td colspan="1" rowspan="1">0.00020778</td></tr><tr><td colspan="1" rowspan="1">2.10</td><td colspan="1" rowspan="1">0.017864</td><td colspan="1" rowspan="1">2.46</td><td colspan="1" rowspan="1">0.0069469</td><td colspan="1" rowspan="1">2.82</td><td colspan="1" rowspan="1">0.0024012</td><td colspan="1" rowspan="1">3.18</td><td colspan="1" rowspan="1">0.00073638</td><td colspan="1" rowspan="1">3.54</td><td colspan="1" rowspan="1">0.00020006</td></tr><tr><td colspan="1" rowspan="1">2.11</td><td colspan="1" rowspan="1">0.017429</td><td colspan="1" rowspan="1">2.47</td><td colspan="1" rowspan="1">0.0067557</td><td colspan="1" rowspan="1">2.83</td><td colspan="1" rowspan="1">0.0023274</td><td colspan="1" rowspan="1">3.19</td><td colspan="1" rowspan="1">0.00071136</td><td colspan="1" rowspan="1">3.55</td><td colspan="1" rowspan="1">0.00019262</td></tr><tr><td colspan="1" rowspan="1">2.12</td><td colspan="1" rowspan="1">0.017003</td><td colspan="1" rowspan="1">2.48</td><td colspan="1" rowspan="1">0.0065691</td><td colspan="1" rowspan="1">2.84</td><td colspan="1" rowspan="1">0.0022557</td><td colspan="1" rowspan="1">3.20</td><td colspan="1" rowspan="1">0.00068714</td><td colspan="1" rowspan="1">3.56</td><td colspan="1" rowspan="1">0.00018543</td></tr><tr><td colspan="1" rowspan="1">2.13</td><td colspan="1" rowspan="1">0.016586</td><td colspan="1" rowspan="1">2.49</td><td colspan="1" rowspan="1">0.0063872</td><td colspan="1" rowspan="1">2.85</td><td colspan="1" rowspan="1">0.0021860</td><td colspan="1" rowspan="1">3.21</td><td colspan="1" rowspan="1">0.00066367</td><td colspan="1" rowspan="1">3.57</td><td colspan="1" rowspan="1">0.00017849</td></tr><tr><td colspan="1" rowspan="1">2.14</td><td colspan="1" rowspan="1">0.016177</td><td colspan="1" rowspan="1">2.50</td><td colspan="1" rowspan="1">0.0062097</td><td colspan="1" rowspan="1">2.86</td><td colspan="1" rowspan="1">0.0021182</td><td colspan="1" rowspan="1">3.22</td><td colspan="1" rowspan="1">0.00064095</td><td colspan="1" rowspan="1">3.58</td><td colspan="1" rowspan="1">0.00017180</td></tr><tr><td colspan="1" rowspan="1">2.15</td><td colspan="1" rowspan="1">0.015778</td><td colspan="1" rowspan="1">2.51</td><td colspan="1" rowspan="1">0.0060366</td><td colspan="1" rowspan="1">2.87</td><td colspan="1" rowspan="1">0.0020524</td><td colspan="1" rowspan="1">3.23</td><td colspan="1" rowspan="1">0.00061895</td><td colspan="1" rowspan="1">3.59</td><td colspan="1" rowspan="1">0.00016534</td></tr></table>

# สูตรคณิตศาสตร์ที่สำคัญ

ภาคผนวกนี้จะแสดงสูตรคณิตศาสตร์ที่ใช้บ่อยสำหรับการวิเคราะห์ระบบการประมวลผลสัญญาณของ ฮาร์ดดิสก์ไดรฟ์ของหนังสือเล่มนี้

## ข.1 ตรีโกณมิติ (Trigonometric)

$$
\sin ( - \alpha ) = - \sin ( \alpha )
$$

$$
\cos ( - \alpha ) = \cos ( \alpha )
$$

$$
\sin ( \alpha ) = \cos ( \alpha - \pi / 2 )
$$

$$
\sin ^ { 2 } ( \alpha ) + \cos ^ { 2 } ( \alpha ) = 1
$$

$$
\sin ( \alpha \pm \beta ) = \sin ( \alpha ) \cos ( \beta ) \pm \cos ( \alpha ) \sin ( \beta )
$$

$$
\cos ( \alpha \pm \beta ) = \cos ( \alpha ) \cos ( \beta ) \mp \sin ( \alpha ) \sin ( \beta )
$$

$$
\begin{array} { r } { \sin ( \alpha ) \sin ( \beta ) = \frac { 1 } { 2 } \cos ( \alpha - \beta ) - \frac { 1 } { 2 } \cos ( \alpha + \beta ) } \end{array}
$$

$$
\begin{array} { r } { \sin ( \alpha ) \cos ( \beta ) = { \frac { 1 } { 2 } } \sin ( \alpha + \beta ) + { \frac { 1 } { 2 } } \sin ( \alpha - \beta ) } \end{array}
$$

$$
\cos ( \alpha ) \cos ( \beta ) = { \textstyle { \frac { 1 } { 2 } } } \cos ( \alpha - \beta ) + { \textstyle { \frac { 1 } { 2 } } } \cos ( \alpha + \beta )
$$

$$
\begin{array} { r } { \cos ( \alpha ) \sin ( \beta ) = { \frac { 1 } { 2 } } \sin ( \alpha + \beta ) - { \frac { 1 } { 2 } } \sin ( \alpha - \beta ) } \end{array}
$$

$$
\begin{array} { r l } & { \sin ( 2 \alpha ) = 2 \sin ( \alpha ) \cos ( \alpha ) } \\ & { \cos ( 2 \alpha ) = \cos ^ { 2 } ( \alpha ) - \sin ^ { 2 } ( \alpha ) = 1 - 2 \sin ^ { 2 } ( \alpha ) = 2 \cos ^ { 2 } ( \alpha ) - 1 } \\ & { \sin ^ { 2 } ( \alpha ) = \frac { 1 } { 2 } \{ 1 - \cos ( 2 \alpha ) \} } \\ & { \cos ^ { 2 } ( \alpha ) = \frac { 1 } { 2 } \{ 1 + \cos ( 2 \alpha ) \} } \\ & { e ^ { j \alpha } = \cos ( \alpha ) + j \sin ( \alpha ) } \\ & { \sin ( \alpha ) = ( e ^ { j \alpha } - e ^ { - j \alpha } ) / ( 2 j ) } \\ & { \cos ( \alpha ) = ( e ^ { j \alpha } + e ^ { - j \alpha } ) / 2 } \end{array}
$$

## ข.2 ปริพันธ์ไม่จำกัดเขต (Indefinite Integral)

f u dv = uv − f v du เมื่อ น และ V เป็นฟังก์ชันของ x   
f xn dx = xn+1 / (n + 1) เมื่อ n ± −1   
f x−1 dx = ln(x)   
f eax dx = eax /a   
f ln(x) dx = x ln(x) − x   
f xeax dx = eax (ax − 1)/a2   
f x2eax dx = eax (a2x2 − 2ax + 2)/a3   
f sin(ax) dx = −(1/a) cos(ax)   
f cos(ax) dx = (1/a) sin(ax)   
f sin2(ax) dx = x/2 − sin(2ax)/4a   
f x sin(ax) dx = (1/ a2){sin(ax) − ax cos(ax)}   
f cos2(ax) dx = x/2 + sin(2ax)/4a   
f x cos(ax) dx = (1/a2){cos(ax) + ax sin(ax)}

## ภาคผนวก ค

## คำศัพท์เทคนิค

กฎการตัดสินใจ decision rule

กระบวนการเขียน write process

กระบวนการสร้างสัญญาณแอนะ ล็อกให้กลับคืนมา signal reconstruction process

กระบวนการสุ่ม random process

กระบวนการสุ่มเกาส์เซียน Gaussian random process

กระบวนการอ่าน read process

กระ แสไฟฟ้าสำหรับเขียนข้อมูล write current

กลุ่มข้อมูล data packet

การกลำรหัสพัลส์ PCM (pulse code modulation)

การกล้ำสัญญาณ (การมอดูเลต) modulation

การกล้ำ แอมพลิจูดของพัลส์ PAM (pulse amplitude modulation)

การขยายสัญญาณรบกวน noise enhancement

การเข้าจังหวะ synchronization

การเข้าจังหวะอย่างสมบูรณ์ perfect synchronization

การเข้าถึงแบบสุ่ม random access

การคาดหมาย (ค่าคาดหมาย) expectation

การจัดเก็บข้อมูล data storage

การจัดเก็บข้อมูลดิจิทัล digital data storage

การจำลอง simulation

การแจงหน่วย quantization

การฉาย projection

การชดเชยก่อนการเขียน write precompensation   
การชักตัวอย่าง sampling   
การตรวจหาลำดับ sequence detection   
การทดสอบอัตราส่วนความน่าเป็นจริง likelihood ratio test   
การทำคอนโวลูชันทางความถี convolution in frequency   
การทำคอนโวลูชันทางเวลา convolution in time   
การทำคอนโวลูชันที่ต่อเนื่องทางเวลา continuous-time convolution   
การทำคอนโวลูชันที่ไม่ต่อเนื่องทางเวลา di screte-time convolution   
การแทรกสอด interference   
การแทรกสอดระหว่างสัญลักษณ์ ISI (intersymbol interference)   
การบันทึก recording   
การบันทึกทับ (การเขียนทับ) overwrite   
การบันทึกแบบแนวตั้ง perpendicular recording   
การบันทึกแบบแนวนอน longitudinal recording   
การบันทึกแบบไบนารี binary recording   
การบันทึกแบบไฮบริด hybrid recording   
การบันทึกระบบแม่เหล็ก magnetic recording   
การบันทึกระบบแม่เหล็กที่ใช้ความร้อนเข้าช่วย HAMR (heat-assisted magnetic recording)   
การบีบเวลาtime-compression   
การประมวลผลสัญญาณดิจิทัล digital signal processing   
การเปลี่ยนสถานะ transition   
การเปลียนสถานะเอกเทศ isolated transition   
การแปลงซี Z transform   
การแปลงฟูเรียร์ Fourier transform   
การแปลงฟูเรียร์ผกผัน inverse Fourier transform   
การแพร่กระจายของข้อผิดพลาด error propagation   
การแยกสัญญาณ (ดีมอดูเลชัน) demodulation   
การลดทอน attenuation   
การลบล้างบางส่วน partial erasure   
การลบล้างสภาพแม่เหล็ก demagnetization   
การเลื่อนขนานเชิงความถี่ translation   
การเลื่อนตำแหน่งของการเปลี่ยนสถานะ transition shift   
การเลื่อนตำแหน่งของการเปลี่ยนสถานะ แบบแข็ง HTS (hard transition shift)   
การเลื่อนตำแหน่งของการเปลี่ยนสถานะ แบบไม่เป็นเชิงเส้น NLTS (nonliทeลar tranรition shift)   
การเลื่อนตำแหน่งของการเปลี่ยนสถานะ แบบอ่อน ETS (easy transition shift)   
การเลื่อนทางความถี่ frequency shifting   
การเลื่อนทางเวลา time shifting   
การสูญเสียแอมพลิจูดแบบไม่เป็นเชิงเส้น nonlinear amplitude loss   
การเสื่อม degradation   
การหน่วงเวลาการตัดสินใจ decision delay   
การหาปริพันธ์ทางเวลาtime integration   
การหาอนุพันธ์ di fferenti ation   
การหอนุพันธ์ทางเวลา time differentiation   
กำลัง power   
กำลังขณะหนึ่ง instantaneous power   
กำลังเฉลี่ย average power   
กำลังเฉลี่ยทางเวลา time-averaged power   
กำ ลังสองเฉลี่ยที่น้อยสุด LMS (least mean square)   
กิกะบิต Gb (gigabit)   
กิกะไบต์ GB (gigabyte)   
เกรน, เม็ด, เนื้อ grain   
เกาส์เซียน Gaussian   
ขนาด magnitude   
ขอบเขตของสัญญาณรบกวน noise margin   
ข้อผิดพลาด error   
ข้อผิดพลาดการแจงหน่วย quantization error   
ข้อผิดพลาดกำ ลังสองเฉลี่ย MSE (mean-squared error)   
ข้อผิดพลาดกำ ลังสองเฉลี่ยที่น้อยสุด MMsE (minimum mean-squared error)   
ข้อมูลไบนารี binary data   
ข้อมูลวิยุต (แซมเปิล)discrete data   
ควรจะ เป็uมากสุด ML (maximum-likelihood)   
ความกว้างของแทร็กtrack width   
ความขรุขระเชิงความร้อน thermal asperity   
ความเข้มของพลังงาน energy intensity   
ความจุช่องสัญญาณ channel capacity   
ความถีการชักตัวอย่าง sampling frequency   
ความถี่เชิงมุม angular frequency   
ความถี่ตัด cut-off frequency   
ความถี่ไนควิตส์ Nyqui st frequency   
ความถี่มูลฐาน fundamental frequency   
ความน่าจะ เป็น probability   
ความน่าจะ เป็นของข้อผิดพลาด probability of error   
ความแปรปรวน variance   
ความแปรปรวนร่วมเกี่ยว covariance   
ความผิดเพี้ยนของค่าสูงสุด peak distortion   
ความผิดเพียนจุดตัดค่าศูนย์ distortion of zero crossings   
ความผิดเพี้ยนเชิงแบบเชิงเส้น linear distortion   
ความผิดเพี้ยนเชิงเฟสphase distortion   
ความผิดเพี้ยนเชิงแอมพลิจูด amplitนde distortion   
ความผิดเพี้ยนแบบไม่เชิงเส้น nonlinear distortion   
ความผิดเพี้ยนภาพ aliasing   
ความไม่เป็นเชิงเส้น nonlinearity   
ความไวต่อข้อผิดพลาดทางเวลา sensitivity timing error   
ความสัมพันธ์ของพาร์ซิวาล Parseval's relation   
ความสุ่ม randomness   
ความหนาแน่นของการบันทึกแบบนอร์มอลไลซ์ ND (normalized recording density)   
ความหนาแน่นเชิงแทร็ก track density   
ความหนาแน่นเชิงพื้นที่ areal density   
ความหนาแน่นเชิงเส้น linear density   
ความหนาแน่นสเปกตรัม spectral density   
ความหนาแน่นสเปกตรมกำลัง power spectral density   
ความหนาแน่นสเปกตรัมพลังงาน energy spectral density   
ความไหว sensitivity   
คอนโวลูชัน convolution   
ค่ากำลังสองเฉลี่ย mean square   
ค่าคาดหมาย (ค่าเฉลีย) expected value   
ค่าเฉลี่ย mean   
ค่าเฉลี่ยของตัวอย่าง sample mean   
ค่าเฉลี่ยทางเวลา time average   
ค่าเฉลี่ยทางสถิติ statistic average   
ค่าเฉลี่ยเอนเซมเบิล (ค่าเฉลี่ยทั้งชุด) ensemble average   
ค่าตัดสินใจ decision   
คาบ (เวลา) period   
คาบการชักตัวอย่าง sampling period   
คาบมูลฐาน fundamental period   
คาบเวลาของบิต bit period   
ค่าสัมประสิทธิ์ของอีควอไลเซอร์ที่เหมาะที่สุด optimum coefficient   
ค่าสัมประสิทธิ์แอนไอโซทรอปีแบบแกนเดี่ยว uniaxial anisotropy coefficient   
คุณสมบัติการแจกแจง di stributive property   
คุณสมบัติการซ้อนทับ superposition property   
คุณสมบัติการบวก additivity property   
คุณสมบัติการเปลี่ยนหมู่ associative property   
คุณสมบัติการสลับที่ commutative property   
คุณสมบัติคอซอลิดี้ causality property   
คุณสมบัติซิฟต์ทิง sifting property   
คุณสมบัติทวิภาวะ duality property   
คุณสมบัติสเตชันเนรี stationary   
คุณสมบัติเอกพันธ์ scaling property (homogeneity)   
คุณสมบัติเออร์กอดิก ergodicity   
คู่การแปลงฟูเรียร์ Fourier transform pair   
เครือข่าย network   
เครือข่ายเฉพาะทีLAN (local area network)   
เครือข่ายอินเทอร์เน็ต Internet   
เครื่องรับ, วงจร ภาครับ receiver   
เครื่องส่ง, วงจรภาคส่ง transmitter   
เครื่องหมายเข้าจังหวะ sync mark   
งานประ ยุกต์ (แอพลิเคชัน) application   
จาน, จานบันทึก disk   
จานบันทึกแม่เหล็ก magnetic disk   
จิตเตอร์ jitter   
จิตเตอร์ทางเวลา timing jitter   
จุดอิ่มตัว saturation point   
ช่องสัญญาณ channel   
ช่องสัญญาณสื่อสาร communication channe]   
ช่องสัญญาณอ่าน read channel   
ชิปช่องสัญญาณอ่าน read-channel chip   
เชิงเส้น linear   
ซ้อนเหลื่อม overlap   
ซูเปอร์พาราแมกเนติก superparamagnetic   
เซกเตอร์ sector

เซตย่อย subset   
แซมเปิล (ตัวอย่าง) sample   
แซมเปิลที่ถูกแจงหน่วย quantized sample   
ไซนูซอยด์ sinusoidal   
ดิจิทัล digital   
ดีแรม DRAM (dynamic random access memory)   
เดซิเบล dB (decibel)   
โดเมน domain   
โดเมน D D domain   
โดเมน ZZ domain   
โดเมนความถี่ frequency domain   
โดเมนที่ต่อเนื่องทางเวลา continuous-time domain   
โดเมนที่ไม่ต่อเนื่องทางเวลา discrete-time domain   
โดเมนเวลา time domain   
ตัวขับการเขียนwrite driver   
ตัวควบคุมการเคลื่อนไหว actuator   
ตัวคูณร่วมน้อย least common multiple   
ตัวชี้บอก indicator   
ตัวดำเนินการคอนโวลูชัน convolution operator   
ตัวดำเนินการค่าคาดหมาย expectation operator   
ตัวดำเนินการหน่วงเวลา delay operator   
ตัวไดรฟ์drive   
ตัวประ กอบโร ลล์ออฟroll-off factor   
ตัวแปรสุ่ม random variable   
ตัวแปรสุ่มวิยุต discrete random variable   
ตัวแปรสุมทวินาม binomial random variable   
ตัวแปรสุ่มเบอร์นูลี bernoulli random variable   
ตัวสไลเดอร์ slider   
ตารางค้นหา look-up table   
แถบบันทึก (แถบ) tape   
แถบบันทึกกระดาษ paper tape   
แถบแม่เหล็กmagnetic tape   
แถวลำดับ (อะเรย์)array   
ทฤษฎีบทการ ชักตัวอย่าง sampling theorem   
ทฤษฎีบทการ ชักตัวอย่างของในควิตส์Nyqui st's sampling theorem

ทฤษฎีบทของเบส์ Bayes' theorem   
ทฤษฎีบทพลังงานของเรย์ลี Rayleigh's energy theorem   
ทาร์เก็ต target   
ทาร์เก็ตแบบ GPR generalized partial-response (GPR) target   
ทาร์เก็ตแบบ PR partial-response target   
ทำให้เป็นบรรทัดฐาน normalize   
เทคนิคการบังคับให้เป็นศูนย์ zero-forcing technique   
เทระไบต์ TB (terabyte)   
แท็ป tap   
แทร็ก (วง หรือ ร่อง) track   
ไทมมิ่งริ คัฟเวอรี timing recovery   
บัตรเจาะรู punch card   
บิต bit   
บิตข่าวสาร message bit   
บิตเซลล์ T (คาบเวลาของหนึ่งบิต) bit cell   
บิตเปลี่ยนสถานะ transition bit   
บิตส่วนเกิน redundant bit   
แบนด์วิดท์ bandwidth   
แบนด์วิดท์แบบศูนย์ถึงศูนย์ null-to-null bandwidth   
แบบข้อมูล data pattern   
แบบจำลอง model   
แบบจำ ลองช่องสัญญาณที่ไม่ต่อเนื่องทางเวลาแบบสมมูล equivalent discrete-time channel model   
ไบต์ (1 ไบต์ = 8 บิต) byte   
ไบนารี (ฐานสอง) binary   
ประเภทของหัวแม่เหล็กชนิดหนึ่ง MR (magneto-resistive)   
ประสิทธิภาพแบนด์วิดท์bandwidth efficiency   
ปรับ (ให้เป็นปัจจุบัน)update   
ปริภูมิตัวอย่างsample space   
ผลตอบสนอง response   
ผลตอบสนองการเปลี่ยนสถานะ transition response   
ผลตอบสนองของระบบ system response   
ผลตอบสนองเชิงความถี่ frequency response   
ผลตอบสนองไดบิต dibit response   
ผลตอบสนองบางส่วน PR (partial response)   
ผลตอบสนองบางส่วนควรจะ เป็นมากสุดPRML (partial-response maximum-likelihood)   
ผลตอบสนองบางส่วนแบบทั่วไป GPR (generalized partial-response)   
ผลตอบสนองอิมพัลส์ impulse response   
แผงควบคุมวงจรไฟฟ้า printed circuit board   
แผ่นชีดี CD (compact disc)   
แผ่นดีวีดี DVD (digital versatile disc)   
แผ่นบันทึก floppy disk   
แผ่นบันทึกแม่เหล็ก magnetic floppy disk   
แผนภาพ diagram   
แผนภาพดวงตา eye diagram   
พฤติกรรมเชิงเฉลี่ย average behavior   
พลังงาน energy   
พลังงานเชิงความร้อน thermal energy   
พลังงานบิตเฉลี่ย average bit energy   
พลังงานหนึ่งหน่วย unit energy   
พหุนาม polynomial   
พื้นข้อผิดพลาด error floor   
โพรบ (หัวตรวจ) probe   
ฟลักซ์fux   
ฟังก์ชันfunction   
ฟังก์ชันก่อกำเนิด generating function   
ฟังก์ ชันการ แจกแจงความน่าจะ เป็น cumulative di stribution function   
ฟังก์ ชันการชักตัวอย่าง sampling function   
ฟังก์ชันกำ ลังสอง quadratic function   
ฟังก์ชันขั้นหนึ่งหน่วยunit step function   
ฟังก์ ชันความหนาแน่นความน่าจะ เป็นprobability density function   
ฟังก์ชันความหนาแน่นความน่าจะ เป็นก่อน a-priori probability density function   
ฟังก์ ชันความหนาแน่นความน่าจะ เป็นแบบเกาส์เซียนGaussiaท probability density function   
ฟังก์ ชันความหนาแน่นความน่าจะ เป็นมีเงื่อนไขconditional probability density function   
ฟังก์ชันคู่ even funtion   
ฟังก์ชันโครเนคเกอร์ เดลตา Kronecker delta function   
ฟังก์ชันซิงก์ sinc function   
ฟังก์ ชันเดลตา Delta function   
ฟังก์ชันไดเรคเดลตาDirac delta function   
ฟังก์ ชันถ่ายโอนtransfer function   
ฟังก์ ชันอัตสหสัมพันธ์เฉลี่ยทางเวลา time-averaged auto-correlation function

ฟังก์ชันอิมพัลส์ impulse function

ฟิล์มบาง thin film

เฟร์ไรต์ ferrite

ไฟฟ้ากระแสตรง d.c. (direct current)

ภาวะ mode

ภาวะการได้มา acqui sition mode

ภาวะการติดตาม tracking mode

ภาวะการฝึกอบรม training mode

ภาวะ เกรนหยาบ (สภาพการเป็นเม็ด) granularity

มอดูเลชัน (การกล้ำสัญญาน) modulation

มอเตอร์สปินเดิล (มอเตอร์กระสวย) spindle motor

มัลติเพล็กซ์ (สหสัญญาณ) multiplex

เมกะไบต์ MB (megabyte)

เมทริกซ์อัตสหสัมพันธ์ auto-correlation matrix

ไมโครโพรเซสเซอร์ microprocessor

ไม่มีสหสัมพันธ์กัน uncorrelated

รหัส RLL run-length limited (RLL) code

ร หัสแก้ไขข้อผิดพลาด ECC (error-correction code)

รหัสมอดูเลชัน modulation code

ระดับการแจงหน่วย quantization level

ระบบการจัดเก็บข้อมูล data storage system

ระบบการบันทึกแบบแนวตั้ง perpendicular recording system

ระบบการบันทึกแบบแนวนอน longitudinal recording system

ระบบการบันทึกแม่เหล็ก magnetic recording system

ระบบการส่งสัญญาณแถบความถี่ฐาน baseband transmi ssion system

ระบบเชิงเส้นที่ไม่แปร เปลี่ยนตามเวลา linear time-invariant (LTI) system

ระบบที่ไม่ต่อเนื่องทางเวลา discrete-time system

ระบบที่ไม่แปรเปลี่ยนตามเวลา time-invariant system

ระบบที่สามารถส่งผ่านสัญญาณได้โดยไม่ผิดเพียน di stortionless system

ระบบไบนารี binary system

ระบบสือสาร communication system

ระบบสื่อสารดิจิทัล digital communication system

ระยะทางกำลังสองเฉลี่ย MSD (mean-squared distance)

รูปคลื่น waveform

รูปแบบข้อมูล data format

เรจิสเตอร์แบบเลื่อน shift register   
ล่วงหน้าเวลา advance   
ลำดับ sequence   
ลำดับข้อมู ล data sequence   
ลำดับข้อมูลเปลี่ยนสถานะ transition data sequence   
ลิมิตแชนนอน Shannon limit   
ลูปฮิสเทอรีซิส Hysteresis loop   
เลื่อนเวลา time-shift   
ไลน์โค้ดline code   
วงจรกรอง filter   
วงจรกรองแบบเชิงเส้น linear filter   
วงจรกรองผ่านตำ LPF (low-pass filter)   
วงจรกรองผ่านตำอุดมคติ ideal low-pass filter   
วงจรกรองภาครับ receiving filter   
วงจรกรองภาคส่ง transmitting filter   
วงจรกรองเหมาะสุด matched filter   
วงจรขยายก่อน pre-amplifier   
วงจรขยายแบบแปรผันได้ VGA (variable gain amplifier)   
วงจรเข้ารหัส encoder   
วงจรเข้ารหัสแก้ไขข้อผิดพลาด error-correction code (ECC) encoder   
วงจรเข้ารหัสมอดูเลชัน modulation encoder   
วงจรคู่ควบไฟฟ้ากระ แสสลับ a.c. (alternating current) coupling   
วงจรแจงหน่วย quantizer   
วงจรชักตัวอย่าง sampler   
วงจรตรวจหา detector   
วงจรตรวจหา NPML noise-predictive maximum-likelihood (NPML) detector   
วงจรตรวจหา PRML partial-response maximum-likelihood (PRML) detector   
วงจรตรวจหาขีดเริมเปลียน threshold detector, slicer   
วงจรตรวจหาจุดสูงสุด peak detector   
วงจรตรวจหาแบบ MAP maximum a-posteriori probability (MAP) detector   
วงจรตรวจหาแบบ ML maximum-likelihood (ML) detector   
วงจรตรวจหาลำ ดับที่ควรจะ เป็นมากสุด MLsD (maximum-likelihood sequence detector)   
วงจรตรวจหาวีเทอร์บิViterbi detector   
วงจรตรวจหาสัญลักษณ์ symbol detector   
วงจรถอดรหัสdecoder   
วงจรถอดร หัสแก้ไขข้อผิดพลาด error-correction code (ECC) decoder   
วงจรเปลี่ยนสัญญาณแอนะ ล็อกเป็นสัญญาณดิจิทัลADC (analog-to-digital converter)   
วงจรเฟสล็อกลูป PLL (phase-locked loop)   
วงจรสหสัมพันธ์ correlator   
วงจรหาอนุพันธ์ differentiator   
วงที่พักหัวอ่าน/บันทึก landing zone   
วัสดุแม่เหล็ก magnetic material   
เวกเตอร์หนึ่งหน่วยunit vector   
เวลาที่เหมาะที่สุดสำหรับการชักตัวอย่าง optimum sampling time   
โวลต์volt   
สเตซันเนรี แบบไวด์เซนส์ WSS (wide-sense stationary)   
สูเตชันเนรีแบบสตริกเซนส์ SSS (strict-sense stationary)   
สนามแม่เหล็กของหัวเขียน head magnetic field   
สนามแม่เหล็กตกค้าง remanent magnetic filed   
สเปกตรัม spectrum   
สเปกตรัมของสัญญาณ signal spectrum   
สเปกตรัมค่าศูนย์ spectral null   
สเปกตรัมเชิงเฟส phase spectrum   
สเปกตรัมเชิงแอมพลิจูด amplitนde spectrum   
สเปกตรัมแบบเส้น line spectrum   
สภาพความเป็นแม่เหล็ก (การทำให้เป็นแม่เหล็ก) magnetization   
สภาพความเป็นแม่เหล็กของสื่อบันทึก medium magnetization   
สภาพแม่เหล็กตกค้าง remanent magnetization   
สภาพลบล้างแม่เหล็ก coercivity   
สภาพให้ซึมผ่านได้permeability   
สลับเปลี่ยน (ทรานสโพส) transpose   
ส่วนประกอบ component   
สหสัมพันธุ์ correlation   
สหสัมพันธุ์ข้าม cross-correlation   
สังยุคเชิงซ้อน complex conjugate   
สัจพจน์ axiom   
สัญญาณ signal   
สัญญาณกระตุ้น excitation signal   
สัญญาณกำลัง power signal   
สัญญาณเชิงกำหนด deterministic signal   
สัญญาณตอบสนอง response signal   
สัญญาณแถบความถี่ฐาน baseband signal   
สัญญาณที่ต่อเนื่องทางเวลา continuous-time signal   
สัญญาณที่มีแถบความถี่จำกัด band-limited signal   
สัญญาณที่มีเวลาจำกัด time-limited signal   
สัญญาณที่ไม่ต่อเนื่องทางเวลาdiscrete-time signal   
สัญญาณไบนารี (สัญญาณสองระดับ) binary signal   
สัญญาณเป็นคาบ periodic signal   
สัญญาณพลังงาน energy signal   
สัญญาณพัลส์ RC raised-cosine pulse   
สัญญาณพัลส์ RRC root-raised cosine   
สัญญาณพัลส์ในควิตส์Nyquist pulse   
สัญญาณพัลส์ในควิตส์อุดมคติ ideal Nyquist pulse   
สัญญาณพัลส์เปลี่ยนสถานะ transition pulse   
สัญญาณพัลส์เปลี่ยนสถานะ เอกเทศ isolated transition pulse   
สัญญาณพัลส์รูปดับเลต doublet signal   
สัญญาณพัลส์รูปสี่เหลี่ยม rectangular pulse   
สัญญาณไม่เป็นคาบ non-periodic signal, aperiodic signal   
สัญญาณรบกวน noise   
สัญญาณรบกวนการแจงหน่วย quantization noise   
สัญญาณรบกวนการเปลี่ยนสถานะ transition noise   
สัญญาณรบกวนเกาส์สีขาว white Gaussian noise   
สัญญาณรบกวนเกาส์สีขาวแบบบวก AWGN (additive white Gaussian noise)   
สัญญาณรบกวนความร้อนthermal noise   
สัญญาณรบกวนแบบสี colored noise   
สัญญาณรบกวนสีขาว white noise   
สัญญาณรบกวนสื่อบันทึก media noise   
สัญญาณรูปคลื่นแรงดันไฟฟ้าที่ได้จากหัวอ่าน สัญญาณ read-back   
สัญญาณสุ่ม random signal   
สัญญาณหลายระดับ multi-level signal   
สัญญาณอิมพัลส์หนึ่งหน่วย unit impulse signal   
สัญญาณแอนะ ล็อกทางไฟฟ้าที่ได้จากหัวอ่าน (สัญญาณ read-back) read-back signal   
สัมประสิทธิ์ coefficient   
สิ่งเปรอะเปือน contamination   
สื่อบันทึก (จานแม่เหล็ก) media (Or medium)   
สื่อบันทึกแม่เหล็กmagnetic media   
สูตรการประมาณค่าในช่วงของในควิตส์และ แชนนอน Nyquist-Shannon interpolation formula   
เส้นเชื่อมฐานbaseline   
เสียงรบกวนจากแถบเสียง modulation noise   
หน่วงเวลา delay   
หน่วยเก็บโพรบprobe storage   
หน่วยความจำของช่องสัญญาณ channel memory   
หน่วยความจำไม่ลบเลือน nonvolatile memory   
หน่วยความจำลบเลือนได้volatile memory   
หน่วยความจำหลักแบบสารกึ่งตัวนำ semiconductor main memory   
หัวเขียน write head   
หัวแม่เหล็ก (หัวอ่านและหัวเขียน) magnetic head   
หัวอ่านread head   
เหตุการณ์ event   
เหตุการณ์ไม่เกิดร่วม mutually exclusive events   
เหมาะที่สุด optimal   
แหล่งต้นทาง source   
แหล่งปลายทาง destination   
อนุภาค (ละอองธุลี) particulate   
อสมการชวาร์ซ Schwarz's inequality   
อัตความแปรปรวนร่วมเกี่ยว auto-covariance   
อัตราการขยาย gain   
อัตราการขยายการเข้ารหัส coding gain   
อัตราการ ชักตัวอย่าง sampling rate   
อัตราการ ลู่เข้า convergence rate   
อัตราข้อผิดพลาดบิต BER (bit-error rate)   
อัตราเจริ ญเติบโต (รายปี) ทบต้น CGR (compound growth rate)   
อัตราบิต bit rate   
อัตรารหัส code rate   
อัตราส่งข้อมูล data rate   
อัตราส่วนค่ากำลังเฉ ลี่ยของสัญญาณที่ต้องการต่อค่ากำ ลังเฉ ลี่ยของสัญญาณรบกวน SNR (signal-to-noise ratio)   
อัตราส่วนค่ากำลังเฉ ลี่ยของสัญญาณที่ต้องการ ต่อค่ากำ ลังเฉ ลี่ยของสัญญาณรบกวนการ แจงหน่วย รQNR (signa to-quantization noise ratio)

อัตสหสัมพันธ์ auto-correlation

อัลกอริทึม (ขั้นตอนวิธี) algorithm

อัลกอริทึม steepest descent steepest descent algorithm

อัลกอริทึมเกรเดียนต์ gradient algorithm

อัลกอริทึมวีเทอร์บิ Viterbi algorithm

อินดักทีฟ (ประเภทของหัวอ่าน) inductive

อินพุต (รับเข้า, นำเข้า) input

อิ่มตัว saturated

อิสระกันเชิงสถิติ stati stically independent

อีควอไลเซอร์ equalizer

อีควอไลเซอร์แบบ TDL tapped-delay-line (TDL) equalizer

อีควอไลเซอร์ แบบปรับตัว adaptive equalizer

อีควอไลเซอร์แบบเส้นตัดขวาง transversal equalizer

อุปกรณ์เก็บข้อมูลเชิงแสง optical storage device

เอนเซมเบิล ensemble

เอนทิดี entity

เอาต์พุต (ส่งออก, นำออก) output

เอาต์พุตของช่องสัญญาณ channel output

แอนไอโซทรอปี anisotropy

แอนะ ล็อก analog

แอมพลิจูด amplitude

ฮอโลกราฟี holography

ฮาร์ดดิสก์ไดรฟ์ hard disk drive

เฮิรตซ์ Hz (hertz)

## บรรณานุกรม

[1] S. X. Wang and A. M. Taratorin, Magnetic information storage technology. San Diego: Academic Press, 1999.

[2] C. Kozierok, "PCGuide: Hard disk drives." Available online at http://www.pcguide.com/ ref/hdd/index.htm.

[3] O. Smith, "Some possible forms of phonograph," Electrical World, pp. 116 – 117, 1888.

[4] V. Poulsen, "The Telegraphone: a magnetic speech recorder," The Electrician, vol. 46, pp. 208 – 210, 1900.

[5] J. W. M. Bergmans, Digital baseband transmission and recording. Boston/London/ Dordrecht: Kluwer Academic Publishers, 1996.

[6] ปิยะ โควินท์ทวีวัฒน์, การประมวลผลสัญญาณสำหรับการจัดเก็บข้อมูลดิจิทัล เล่ม 2: การออก แบบวงจรภาครับ. ศูนย์เทคโนโลยีอิเล็กทรอนิกส์และคอมพิวเตอร์แห่งชาติ (เนคเทค), 2550.

[7] E. Grochowshi, Available online at http://www.hitachigst.com/hdd/hddpdf/tech/ chart02.pdf.

[8] R. D. Cideciyan, F. Dolivo, R. Hermann, W. Hirt, and W. Schott, 'A PRML system for digital magnetic recording," IEEE J. Selected Areas Commun., vol. 10, no. 1, pp. 38 – 56, January 1992.

[9] B. Sklar, Digital communications: fundamentals and applications: Prentice Hall, 2nd-edition, 2001.

[10] Available online at http://www.storagereview.com/guide2000/ref/hdd/op/over.html.

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

[30] ปิยะ โควินท์ทวีวัฒน์, คู่มือโปรแกรมภาษา รCILAB สำหรับผู้ริ่มต้น (พิมพ์ครั้งที่ 2), ศูนย์ผลิต ตำราเรียน, สถาบันเทคโนโลยีพระจอมเกล้าพระนครเหนือ, 2549.

[31] Available online at http://www.mathworks.com

[32] E. Ström, 'Notes of signals and systems," Available online at http://www. s2.chalmers.se/ undergraduate/courses/ess140/doc/Handouts.htm

[33] A. V. Oppenheim, A. S. Willsky, and S. H. Nawab, Signals and systems. New Jersey: Prentice Hall, 2nd-edition, 1997.

[34] ลัญฉกร วุฒิสิทธิกุลกิจ, หลักการไฟฟ้าสื่อสาร, สำนักพิมพ์แห่งจุฬาลงกรณ์มหาวิทยาลัย, จุฬาลงกรณ์มหาวิทยาลัย, 2546.

[35] M. H. Hayes, Statistical digital signal processing and modeling. New York: John Wiley & Sons Inc., 1996.

[36] A. Leon-Garcia, Probability and random processes for electrical engineering. New York: Addison-Wesley Inc., 2nd-edition, 1994.

[37] J. R. Barry, E. A. Lee, and D. G. Messerschmitt, Digital communication. Boston: Kluwer Academic Publishers, 3nd-edition, 2003.

[38] J. G. Proakis, Digital communication. Singapore: McGraw Hill, 4th-edition, 2001.

[39] A. B. Carlson, P. B. Crilly, and J. C. Rutledge, Communication systems. Singapore: McGraw Hill, 4th-edition, 2002.

[40] พรชัย ทรัพย์นิธิ, ระบบสื่อสารดิจิตอล, แผนกตำรา คณะวิศวกรรมศาสตร์, สถาบันเทคโนโลยี พระจอมเกล้าเจ้าคุณทหารลาดกระบัง, 2549.

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

[60] R. D. Hempstead, "Thermally induced pulses in magnetoresistive heads," IBM J. Res. Develop., vol. 18, pp. 547 – 550, November 1974.

[61] M .F. Erden and E. M. Kurtas, "Thermal asperity detection and cancellation in perpendicular magnetic recording systems," IEEE Trans. on Magnetics, vol. 40, no. 3, pp. 1732 – 1737, May 2004.

[62] S. E. Stupp, M. A. Baldwinson, and P. McEwen, "Thermal asperity trends," IEEE Trans. on Magnetics, vol. 35, pp. 752 – 757, Mar 1999.

[63] P. Kovintavewat, "Robustness of per-survivor iterative timing recovery against thermal asperity in perpendicular recording channels," in Proc. of ECTI-cON 2006, Ubon Ratchathani, Thailand, vol. 1/II, pp. 239 - 242, May 10 – 13, 2006.

[64] P. Luo, K. Stoev, F. Liu, M. Lederman, M. Krounbi, M. Re, M. Mallary, G. Bellesis, and S. Marshall, "Experimental study of asymmetry effects in perpendicular recording," IEEE Trans. on Magnetics, vol. 39, no. 5, pp. 2222 – 2224, September 2003.

[65] P. Kovintavewat, "Oversampled timing recovery for magnetic recording channels," in Proc. of ECTI-CON 2006, Ubon Ratchathani, Thailand, vol. I/II, pp. 235 – 238, May 10 - 13, 2006.

## ดรรชนี

preamble, 214, 228, 300

SCILAB, 32

SNR, 148, 242

SQNR, 157, 158

กฎการตัดสินใจ, 173–176   
กระบวนการสร้างสัญญาณแอนะ ล็อกให้กลับคืน มา, 203–206

กระบวนการสุ่ม, 126–141 ค่าเฉลี่ย, 128 ฟังก์ชันอัตสหสัมพันธ์, 128 สเตชันเนรี, 129 แบบสตริกเซนส์ (รรร), 129 แบบไวด์เซนส์ (พรS), 130, 208 อัตความแปรปรวนร่วมเกียว, 128 เกาส์เซียน, 130 เออร์กอดิก, 134

กระบวนการอ่าน, 247, 259

กระบวนการเขียน, 238, 247   
ความไม่เป็นเชิงเส้น, 247

: 0น การกลำรหัสพัลส์ (PCM), 6, 153–162

การชักตัวอย่าง, 154 การเข้ารหัส, 159 การแจงหน่วย, 155 ซ   
การกลำแอมพลิจูดของพัลส์ (PAM), 162–163, 247, 271   
การขยายสัญญาณรบกวน, 215   
การชดเชยก่อนการเขียน, 254   
การชักตัวอย่าง, 154, 206, 281 กระบวนการ, 203 ความถี่, 195, 201 คาบ, 201 ทฤษฎีบท, 201 วงจร, 284 อัตรา, 284 แบบอัตราสัญลักษณ์, 284 แบบเกินจริง, 284   
การทดสอบอัตราส่วนความน่าเป็นจริง, 175   
การบันทึกทับ, 249 อัตราส่วน, 249, 259   
การบันทึกระบบแม่เหล็ก, 6 ความหมาย, 6