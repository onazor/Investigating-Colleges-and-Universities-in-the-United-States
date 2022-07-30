# Investigating Colleges and Universities in the United States

### Exploratory Data Analysis of Universities and Colleges in United States in **R**
This data set contains a number of variables for **777** different universities and colleges in the United States. The variables are:  
> **Private**: Public/private indicator  
> **Apps**: Number of applications received  
> **Accept**: Number of applicants accepted  
> **Enroll**: Number of new students enrolled  
> **Top10perc**: New students from top 10% of high school class  
> **Top25perc**: New students from top 25% of high school class  
> **F.Undergrad**: Number of full-time undergraduates  
> **P.Undergrad**: Number of part-time undergraduates  
> **Outstate**: Out-of-state tuition  
> **Room.Board**: Room and board costs  
> **Books**: Estimated book costs  
> **PhD**: Percent of faculty with Ph.D.’s  
> **Terminal**: Percent of faculty with terminal degree  
> **S.F.Ratio**: Student/faculty ratio  
> **perc.alumni**: Percent of alumni who donate  
> **Expend**: Instructional expenditure per student  
> **Grad.Rate**: Graduation rate

## 1. We read the data by using the language of R.  
We pass this to the variable college. Just make sure that the directory is correct so that the data will be read.


```R
# Open the data set by using the function read.csv
college <- read.csv("H:/Programming/Jupyter Notebook/datasets/College.csv")

# View the data frame
View(college)
```


<table class="dataframe">
<caption>A data.frame: 777 × 19</caption>
<thead>
	<tr><th scope=col>X</th><th scope=col>Private</th><th scope=col>Apps</th><th scope=col>Accept</th><th scope=col>Enroll</th><th scope=col>Top10perc</th><th scope=col>Top25perc</th><th scope=col>F.Undergrad</th><th scope=col>P.Undergrad</th><th scope=col>Outstate</th><th scope=col>Room.Board</th><th scope=col>Books</th><th scope=col>Personal</th><th scope=col>PhD</th><th scope=col>Terminal</th><th scope=col>S.F.Ratio</th><th scope=col>perc.alumni</th><th scope=col>Expend</th><th scope=col>Grad.Rate</th></tr>
	<tr><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;int&gt;</th><th scope=col>&lt;int&gt;</th><th scope=col>&lt;int&gt;</th><th scope=col>&lt;int&gt;</th><th scope=col>&lt;int&gt;</th><th scope=col>&lt;int&gt;</th><th scope=col>&lt;int&gt;</th><th scope=col>&lt;int&gt;</th><th scope=col>&lt;int&gt;</th><th scope=col>&lt;int&gt;</th><th scope=col>&lt;int&gt;</th><th scope=col>&lt;int&gt;</th><th scope=col>&lt;int&gt;</th><th scope=col>&lt;dbl&gt;</th><th scope=col>&lt;int&gt;</th><th scope=col>&lt;int&gt;</th><th scope=col>&lt;int&gt;</th></tr>
</thead>
<tbody>
	<tr><td>Abilene Christian University           </td><td>Yes</td><td> 1660</td><td> 1232</td><td> 721</td><td>23</td><td>52</td><td> 2885</td><td> 537</td><td> 7440</td><td>3300</td><td>450</td><td>2200</td><td>70</td><td> 78</td><td>18.1</td><td>12</td><td> 7041</td><td> 60</td></tr>
	<tr><td>Adelphi University                     </td><td>Yes</td><td> 2186</td><td> 1924</td><td> 512</td><td>16</td><td>29</td><td> 2683</td><td>1227</td><td>12280</td><td>6450</td><td>750</td><td>1500</td><td>29</td><td> 30</td><td>12.2</td><td>16</td><td>10527</td><td> 56</td></tr>
	<tr><td>Adrian College                         </td><td>Yes</td><td> 1428</td><td> 1097</td><td> 336</td><td>22</td><td>50</td><td> 1036</td><td>  99</td><td>11250</td><td>3750</td><td>400</td><td>1165</td><td>53</td><td> 66</td><td>12.9</td><td>30</td><td> 8735</td><td> 54</td></tr>
	<tr><td>Agnes Scott College                    </td><td>Yes</td><td>  417</td><td>  349</td><td> 137</td><td>60</td><td>89</td><td>  510</td><td>  63</td><td>12960</td><td>5450</td><td>450</td><td> 875</td><td>92</td><td> 97</td><td> 7.7</td><td>37</td><td>19016</td><td> 59</td></tr>
	<tr><td>Alaska Pacific University              </td><td>Yes</td><td>  193</td><td>  146</td><td>  55</td><td>16</td><td>44</td><td>  249</td><td> 869</td><td> 7560</td><td>4120</td><td>800</td><td>1500</td><td>76</td><td> 72</td><td>11.9</td><td> 2</td><td>10922</td><td> 15</td></tr>
	<tr><td>Albertson College                      </td><td>Yes</td><td>  587</td><td>  479</td><td> 158</td><td>38</td><td>62</td><td>  678</td><td>  41</td><td>13500</td><td>3335</td><td>500</td><td> 675</td><td>67</td><td> 73</td><td> 9.4</td><td>11</td><td> 9727</td><td> 55</td></tr>
	<tr><td>Albertus Magnus College                </td><td>Yes</td><td>  353</td><td>  340</td><td> 103</td><td>17</td><td>45</td><td>  416</td><td> 230</td><td>13290</td><td>5720</td><td>500</td><td>1500</td><td>90</td><td> 93</td><td>11.5</td><td>26</td><td> 8861</td><td> 63</td></tr>
	<tr><td>Albion College                         </td><td>Yes</td><td> 1899</td><td> 1720</td><td> 489</td><td>37</td><td>68</td><td> 1594</td><td>  32</td><td>13868</td><td>4826</td><td>450</td><td> 850</td><td>89</td><td>100</td><td>13.7</td><td>37</td><td>11487</td><td> 73</td></tr>
	<tr><td>Albright College                       </td><td>Yes</td><td> 1038</td><td>  839</td><td> 227</td><td>30</td><td>63</td><td>  973</td><td> 306</td><td>15595</td><td>4400</td><td>300</td><td> 500</td><td>79</td><td> 84</td><td>11.3</td><td>23</td><td>11644</td><td> 80</td></tr>
	<tr><td>Alderson-Broaddus College              </td><td>Yes</td><td>  582</td><td>  498</td><td> 172</td><td>21</td><td>44</td><td>  799</td><td>  78</td><td>10468</td><td>3380</td><td>660</td><td>1800</td><td>40</td><td> 41</td><td>11.5</td><td>15</td><td> 8991</td><td> 52</td></tr>
	<tr><td>Alfred University                      </td><td>Yes</td><td> 1732</td><td> 1425</td><td> 472</td><td>37</td><td>75</td><td> 1830</td><td> 110</td><td>16548</td><td>5406</td><td>500</td><td> 600</td><td>82</td><td> 88</td><td>11.3</td><td>31</td><td>10932</td><td> 73</td></tr>
	<tr><td>Allegheny College                      </td><td>Yes</td><td> 2652</td><td> 1900</td><td> 484</td><td>44</td><td>77</td><td> 1707</td><td>  44</td><td>17080</td><td>4440</td><td>400</td><td> 600</td><td>73</td><td> 91</td><td> 9.9</td><td>41</td><td>11711</td><td> 76</td></tr>
	<tr><td>Allentown Coll. of St. Francis de Sales</td><td>Yes</td><td> 1179</td><td>  780</td><td> 290</td><td>38</td><td>64</td><td> 1130</td><td> 638</td><td> 9690</td><td>4785</td><td>600</td><td>1000</td><td>60</td><td> 84</td><td>13.3</td><td>21</td><td> 7940</td><td> 74</td></tr>
	<tr><td>Alma College                           </td><td>Yes</td><td> 1267</td><td> 1080</td><td> 385</td><td>44</td><td>73</td><td> 1306</td><td>  28</td><td>12572</td><td>4552</td><td>400</td><td> 400</td><td>79</td><td> 87</td><td>15.3</td><td>32</td><td> 9305</td><td> 68</td></tr>
	<tr><td>Alverno College                        </td><td>Yes</td><td>  494</td><td>  313</td><td> 157</td><td>23</td><td>46</td><td> 1317</td><td>1235</td><td> 8352</td><td>3640</td><td>650</td><td>2449</td><td>36</td><td> 69</td><td>11.1</td><td>26</td><td> 8127</td><td> 55</td></tr>
	<tr><td>American International College         </td><td>Yes</td><td> 1420</td><td> 1093</td><td> 220</td><td> 9</td><td>22</td><td> 1018</td><td> 287</td><td> 8700</td><td>4780</td><td>450</td><td>1400</td><td>78</td><td> 84</td><td>14.7</td><td>19</td><td> 7355</td><td> 69</td></tr>
	<tr><td>Amherst College                        </td><td>Yes</td><td> 4302</td><td>  992</td><td> 418</td><td>83</td><td>96</td><td> 1593</td><td>   5</td><td>19760</td><td>5300</td><td>660</td><td>1598</td><td>93</td><td> 98</td><td> 8.4</td><td>63</td><td>21424</td><td>100</td></tr>
	<tr><td>Anderson University                    </td><td>Yes</td><td> 1216</td><td>  908</td><td> 423</td><td>19</td><td>40</td><td> 1819</td><td> 281</td><td>10100</td><td>3520</td><td>550</td><td>1100</td><td>48</td><td> 61</td><td>12.1</td><td>14</td><td> 7994</td><td> 59</td></tr>
	<tr><td>Andrews University                     </td><td>Yes</td><td> 1130</td><td>  704</td><td> 322</td><td>14</td><td>23</td><td> 1586</td><td> 326</td><td> 9996</td><td>3090</td><td>900</td><td>1320</td><td>62</td><td> 66</td><td>11.5</td><td>18</td><td>10908</td><td> 46</td></tr>
	<tr><td>Angelo State University                </td><td>No </td><td> 3540</td><td> 2001</td><td>1016</td><td>24</td><td>54</td><td> 4190</td><td>1512</td><td> 5130</td><td>3592</td><td>500</td><td>2000</td><td>60</td><td> 62</td><td>23.1</td><td> 5</td><td> 4010</td><td> 34</td></tr>
	<tr><td>Antioch University                     </td><td>Yes</td><td>  713</td><td>  661</td><td> 252</td><td>25</td><td>44</td><td>  712</td><td>  23</td><td>15476</td><td>3336</td><td>400</td><td>1100</td><td>69</td><td> 82</td><td>11.3</td><td>35</td><td>42926</td><td> 48</td></tr>
	<tr><td>Appalachian State University           </td><td>No </td><td> 7313</td><td> 4664</td><td>1910</td><td>20</td><td>63</td><td> 9940</td><td>1035</td><td> 6806</td><td>2540</td><td> 96</td><td>2000</td><td>83</td><td> 96</td><td>18.3</td><td>14</td><td> 5854</td><td> 70</td></tr>
	<tr><td>Aquinas College                        </td><td>Yes</td><td>  619</td><td>  516</td><td> 219</td><td>20</td><td>51</td><td> 1251</td><td> 767</td><td>11208</td><td>4124</td><td>350</td><td>1615</td><td>55</td><td> 65</td><td>12.7</td><td>25</td><td> 6584</td><td> 65</td></tr>
	<tr><td>Arizona State University Main campus   </td><td>No </td><td>12809</td><td>10308</td><td>3761</td><td>24</td><td>49</td><td>22593</td><td>7585</td><td> 7434</td><td>4850</td><td>700</td><td>2100</td><td>88</td><td> 93</td><td>18.9</td><td> 5</td><td> 4602</td><td> 48</td></tr>
	<tr><td>Arkansas College (Lyon College)        </td><td>Yes</td><td>  708</td><td>  334</td><td> 166</td><td>46</td><td>74</td><td>  530</td><td> 182</td><td> 8644</td><td>3922</td><td>500</td><td> 800</td><td>79</td><td> 88</td><td>12.6</td><td>24</td><td>14579</td><td> 54</td></tr>
	<tr><td>Arkansas Tech University               </td><td>No </td><td> 1734</td><td> 1729</td><td> 951</td><td>12</td><td>52</td><td> 3602</td><td> 939</td><td> 3460</td><td>2650</td><td>450</td><td>1000</td><td>57</td><td> 60</td><td>19.6</td><td> 5</td><td> 4739</td><td> 48</td></tr>
	<tr><td>Assumption College                     </td><td>Yes</td><td> 2135</td><td> 1700</td><td> 491</td><td>23</td><td>59</td><td> 1708</td><td> 689</td><td>12000</td><td>5920</td><td>500</td><td> 500</td><td>93</td><td> 93</td><td>13.8</td><td>30</td><td> 7100</td><td> 88</td></tr>
	<tr><td>Auburn University-Main Campus          </td><td>No </td><td> 7548</td><td> 6791</td><td>3070</td><td>25</td><td>57</td><td>16262</td><td>1716</td><td> 6300</td><td>3933</td><td>600</td><td>1908</td><td>85</td><td> 91</td><td>16.7</td><td>18</td><td> 6642</td><td> 69</td></tr>
	<tr><td>Augsburg College                       </td><td>Yes</td><td>  662</td><td>  513</td><td> 257</td><td>12</td><td>30</td><td> 2074</td><td> 726</td><td>11902</td><td>4372</td><td>540</td><td> 950</td><td>65</td><td> 65</td><td>12.8</td><td>31</td><td> 7836</td><td> 58</td></tr>
	<tr><td>Augustana College IL                   </td><td>Yes</td><td> 1879</td><td> 1658</td><td> 497</td><td>36</td><td>69</td><td> 1950</td><td>  38</td><td>13353</td><td>4173</td><td>540</td><td> 821</td><td>78</td><td> 83</td><td>12.7</td><td>40</td><td> 9220</td><td> 71</td></tr>
	<tr><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td></tr>
	<tr><td>Westfield State College              </td><td>No </td><td> 3100</td><td>2150</td><td> 825</td><td> 3</td><td>20</td><td>3234</td><td> 941</td><td> 5542</td><td>3788</td><td>500</td><td>1300</td><td>75</td><td>79</td><td>15.7</td><td>20</td><td> 4222</td><td>65</td></tr>
	<tr><td>Westminster College MO               </td><td>Yes</td><td>  662</td><td> 553</td><td> 184</td><td>20</td><td>43</td><td> 665</td><td>  37</td><td>10720</td><td>4050</td><td>600</td><td>1650</td><td>66</td><td>70</td><td>12.5</td><td>20</td><td> 7925</td><td>62</td></tr>
	<tr><td>Westminster College                  </td><td>Yes</td><td>  996</td><td> 866</td><td> 377</td><td>29</td><td>58</td><td>1411</td><td>  72</td><td>12065</td><td>3615</td><td>430</td><td> 685</td><td>62</td><td>78</td><td>12.5</td><td>41</td><td> 8596</td><td>80</td></tr>
	<tr><td>Westminster College of Salt Lake City</td><td>Yes</td><td>  917</td><td> 720</td><td> 213</td><td>21</td><td>60</td><td> 979</td><td> 743</td><td> 8820</td><td>4050</td><td>600</td><td>2025</td><td>68</td><td>83</td><td>10.5</td><td>34</td><td> 7170</td><td>50</td></tr>
	<tr><td>Westmont College                     </td><td>No </td><td>  950</td><td> 713</td><td> 351</td><td>42</td><td>72</td><td>1276</td><td>   9</td><td>14320</td><td>5304</td><td>490</td><td>1410</td><td>77</td><td>77</td><td>14.9</td><td>17</td><td> 8837</td><td>87</td></tr>
	<tr><td>Wheaton College IL                   </td><td>Yes</td><td> 1432</td><td> 920</td><td> 548</td><td>56</td><td>84</td><td>2200</td><td>  56</td><td>11480</td><td>4200</td><td>530</td><td>1400</td><td>81</td><td>83</td><td>12.7</td><td>40</td><td>11916</td><td>85</td></tr>
	<tr><td>Westminster College PA               </td><td>Yes</td><td> 1738</td><td>1373</td><td> 417</td><td>21</td><td>55</td><td>1335</td><td>  30</td><td>18460</td><td>5970</td><td>700</td><td> 850</td><td>92</td><td>96</td><td>13.2</td><td>41</td><td>22704</td><td>71</td></tr>
	<tr><td>Wheeling Jesuit College              </td><td>Yes</td><td>  903</td><td> 755</td><td> 213</td><td>15</td><td>49</td><td> 971</td><td> 305</td><td>10500</td><td>4545</td><td>600</td><td> 600</td><td>66</td><td>71</td><td>14.1</td><td>27</td><td> 7494</td><td>72</td></tr>
	<tr><td>Whitman College                      </td><td>Yes</td><td> 1861</td><td> 998</td><td> 359</td><td>45</td><td>77</td><td>1220</td><td>  46</td><td>16670</td><td>4900</td><td>750</td><td> 800</td><td>80</td><td>83</td><td>10.5</td><td>51</td><td>13198</td><td>72</td></tr>
	<tr><td>Whittier College                     </td><td>Yes</td><td> 1681</td><td>1069</td><td> 344</td><td>35</td><td>63</td><td>1235</td><td>  30</td><td>16249</td><td>5699</td><td>500</td><td>1998</td><td>84</td><td>92</td><td>13.6</td><td>29</td><td>11778</td><td>52</td></tr>
	<tr><td>Whitworth College                    </td><td>Yes</td><td> 1121</td><td> 926</td><td> 372</td><td>43</td><td>70</td><td>1270</td><td> 160</td><td>12660</td><td>4500</td><td>678</td><td>2424</td><td>80</td><td>80</td><td>16.9</td><td>20</td><td> 8328</td><td>80</td></tr>
	<tr><td>Widener University                   </td><td>Yes</td><td> 2139</td><td>1492</td><td> 502</td><td>24</td><td>64</td><td>2186</td><td>2171</td><td>12350</td><td>5370</td><td>500</td><td>1350</td><td>88</td><td>86</td><td>12.6</td><td>19</td><td> 9603</td><td>63</td></tr>
	<tr><td>Wilkes University                    </td><td>Yes</td><td> 1631</td><td>1431</td><td> 434</td><td>15</td><td>36</td><td>1803</td><td> 603</td><td>11150</td><td>5130</td><td>550</td><td>1260</td><td>78</td><td>92</td><td>13.3</td><td>24</td><td> 8543</td><td>67</td></tr>
	<tr><td>Willamette University                </td><td>Yes</td><td> 1658</td><td>1327</td><td> 395</td><td>49</td><td>80</td><td>1595</td><td> 159</td><td>14800</td><td>4620</td><td>400</td><td> 790</td><td>91</td><td>94</td><td>13.3</td><td>37</td><td>10779</td><td>68</td></tr>
	<tr><td>William Jewell College               </td><td>Yes</td><td>  663</td><td> 547</td><td> 315</td><td>32</td><td>67</td><td>1279</td><td>  75</td><td>10060</td><td>2970</td><td>500</td><td>2600</td><td>74</td><td>80</td><td>11.2</td><td>19</td><td> 7885</td><td>59</td></tr>
	<tr><td>William Woods University             </td><td>Yes</td><td>  469</td><td> 435</td><td> 227</td><td>17</td><td>39</td><td> 851</td><td> 120</td><td>10535</td><td>4365</td><td>550</td><td>3700</td><td>39</td><td>66</td><td>12.9</td><td>16</td><td> 7438</td><td>52</td></tr>
	<tr><td>Williams College                     </td><td>Yes</td><td> 4186</td><td>1245</td><td> 526</td><td>81</td><td>96</td><td>1988</td><td>  29</td><td>19629</td><td>5790</td><td>500</td><td>1200</td><td>94</td><td>99</td><td> 9.0</td><td>64</td><td>22014</td><td>99</td></tr>
	<tr><td>Wilson College                       </td><td>Yes</td><td>  167</td><td> 130</td><td>  46</td><td>16</td><td>50</td><td> 199</td><td> 676</td><td>11428</td><td>5084</td><td>450</td><td> 475</td><td>67</td><td>76</td><td> 8.3</td><td>43</td><td>10291</td><td>67</td></tr>
	<tr><td>Wingate College                      </td><td>Yes</td><td> 1239</td><td>1017</td><td> 383</td><td>10</td><td>34</td><td>1207</td><td> 157</td><td> 7820</td><td>3400</td><td>550</td><td>1550</td><td>69</td><td>81</td><td>13.9</td><td> 8</td><td> 7264</td><td>91</td></tr>
	<tr><td>Winona State University              </td><td>No </td><td> 3325</td><td>2047</td><td>1301</td><td>20</td><td>45</td><td>5800</td><td> 872</td><td> 4200</td><td>2700</td><td>300</td><td>1200</td><td>53</td><td>60</td><td>20.2</td><td>18</td><td> 5318</td><td>58</td></tr>
	<tr><td>Winthrop University                  </td><td>No </td><td> 2320</td><td>1805</td><td> 769</td><td>24</td><td>61</td><td>3395</td><td> 670</td><td> 6400</td><td>3392</td><td>580</td><td>2150</td><td>71</td><td>80</td><td>12.8</td><td>26</td><td> 6729</td><td>59</td></tr>
	<tr><td>Wisconsin Lutheran College           </td><td>Yes</td><td>  152</td><td> 128</td><td>  75</td><td>17</td><td>41</td><td> 282</td><td>  22</td><td> 9100</td><td>3700</td><td>500</td><td>1400</td><td>48</td><td>48</td><td> 8.5</td><td>26</td><td> 8960</td><td>50</td></tr>
	<tr><td>Wittenberg University                </td><td>Yes</td><td> 1979</td><td>1739</td><td> 575</td><td>42</td><td>68</td><td>1980</td><td> 144</td><td>15948</td><td>4404</td><td>400</td><td> 800</td><td>82</td><td>95</td><td>12.8</td><td>29</td><td>10414</td><td>78</td></tr>
	<tr><td>Wofford College                      </td><td>Yes</td><td> 1501</td><td> 935</td><td> 273</td><td>51</td><td>83</td><td>1059</td><td>  34</td><td>12680</td><td>4150</td><td>605</td><td>1440</td><td>91</td><td>92</td><td>15.3</td><td>42</td><td> 7875</td><td>75</td></tr>
	<tr><td>Worcester Polytechnic Institute      </td><td>Yes</td><td> 2768</td><td>2314</td><td> 682</td><td>49</td><td>86</td><td>2802</td><td>  86</td><td>15884</td><td>5370</td><td>530</td><td> 730</td><td>92</td><td>94</td><td>15.2</td><td>34</td><td>10774</td><td>82</td></tr>
	<tr><td>Worcester State College              </td><td>No </td><td> 2197</td><td>1515</td><td> 543</td><td> 4</td><td>26</td><td>3089</td><td>2029</td><td> 6797</td><td>3900</td><td>500</td><td>1200</td><td>60</td><td>60</td><td>21.0</td><td>14</td><td> 4469</td><td>40</td></tr>
	<tr><td>Xavier University                    </td><td>Yes</td><td> 1959</td><td>1805</td><td> 695</td><td>24</td><td>47</td><td>2849</td><td>1107</td><td>11520</td><td>4960</td><td>600</td><td>1250</td><td>73</td><td>75</td><td>13.3</td><td>31</td><td> 9189</td><td>83</td></tr>
	<tr><td>Xavier University of Louisiana       </td><td>Yes</td><td> 2097</td><td>1915</td><td> 695</td><td>34</td><td>61</td><td>2793</td><td> 166</td><td> 6900</td><td>4200</td><td>617</td><td> 781</td><td>67</td><td>75</td><td>14.4</td><td>20</td><td> 8323</td><td>49</td></tr>
	<tr><td>Yale University                      </td><td>Yes</td><td>10705</td><td>2453</td><td>1317</td><td>95</td><td>99</td><td>5217</td><td>  83</td><td>19840</td><td>6510</td><td>630</td><td>2115</td><td>96</td><td>96</td><td> 5.8</td><td>49</td><td>40386</td><td>99</td></tr>
	<tr><td>York College of Pennsylvania         </td><td>Yes</td><td> 2989</td><td>1855</td><td> 691</td><td>28</td><td>63</td><td>2988</td><td>1726</td><td> 4990</td><td>3560</td><td>500</td><td>1250</td><td>75</td><td>75</td><td>18.1</td><td>28</td><td> 4509</td><td>99</td></tr>
</tbody>
</table>



We should notice that the first column is just the name of each university. We don’t really want R to treat this as data. However, it may be handy to have these names for later.


```R
# Change the index
rownames(college) <- college[, 1]
college <- college[, -1]

View(college)
```


<table class="dataframe">
<caption>A data.frame: 777 × 18</caption>
<thead>
	<tr><th></th><th scope=col>Private</th><th scope=col>Apps</th><th scope=col>Accept</th><th scope=col>Enroll</th><th scope=col>Top10perc</th><th scope=col>Top25perc</th><th scope=col>F.Undergrad</th><th scope=col>P.Undergrad</th><th scope=col>Outstate</th><th scope=col>Room.Board</th><th scope=col>Books</th><th scope=col>Personal</th><th scope=col>PhD</th><th scope=col>Terminal</th><th scope=col>S.F.Ratio</th><th scope=col>perc.alumni</th><th scope=col>Expend</th><th scope=col>Grad.Rate</th></tr>
	<tr><th></th><th scope=col>&lt;chr&gt;</th><th scope=col>&lt;int&gt;</th><th scope=col>&lt;int&gt;</th><th scope=col>&lt;int&gt;</th><th scope=col>&lt;int&gt;</th><th scope=col>&lt;int&gt;</th><th scope=col>&lt;int&gt;</th><th scope=col>&lt;int&gt;</th><th scope=col>&lt;int&gt;</th><th scope=col>&lt;int&gt;</th><th scope=col>&lt;int&gt;</th><th scope=col>&lt;int&gt;</th><th scope=col>&lt;int&gt;</th><th scope=col>&lt;int&gt;</th><th scope=col>&lt;dbl&gt;</th><th scope=col>&lt;int&gt;</th><th scope=col>&lt;int&gt;</th><th scope=col>&lt;int&gt;</th></tr>
</thead>
<tbody>
	<tr><th scope=row>Abilene Christian University</th><td>Yes</td><td> 1660</td><td> 1232</td><td> 721</td><td>23</td><td>52</td><td> 2885</td><td> 537</td><td> 7440</td><td>3300</td><td>450</td><td>2200</td><td>70</td><td> 78</td><td>18.1</td><td>12</td><td> 7041</td><td> 60</td></tr>
	<tr><th scope=row>Adelphi University</th><td>Yes</td><td> 2186</td><td> 1924</td><td> 512</td><td>16</td><td>29</td><td> 2683</td><td>1227</td><td>12280</td><td>6450</td><td>750</td><td>1500</td><td>29</td><td> 30</td><td>12.2</td><td>16</td><td>10527</td><td> 56</td></tr>
	<tr><th scope=row>Adrian College</th><td>Yes</td><td> 1428</td><td> 1097</td><td> 336</td><td>22</td><td>50</td><td> 1036</td><td>  99</td><td>11250</td><td>3750</td><td>400</td><td>1165</td><td>53</td><td> 66</td><td>12.9</td><td>30</td><td> 8735</td><td> 54</td></tr>
	<tr><th scope=row>Agnes Scott College</th><td>Yes</td><td>  417</td><td>  349</td><td> 137</td><td>60</td><td>89</td><td>  510</td><td>  63</td><td>12960</td><td>5450</td><td>450</td><td> 875</td><td>92</td><td> 97</td><td> 7.7</td><td>37</td><td>19016</td><td> 59</td></tr>
	<tr><th scope=row>Alaska Pacific University</th><td>Yes</td><td>  193</td><td>  146</td><td>  55</td><td>16</td><td>44</td><td>  249</td><td> 869</td><td> 7560</td><td>4120</td><td>800</td><td>1500</td><td>76</td><td> 72</td><td>11.9</td><td> 2</td><td>10922</td><td> 15</td></tr>
	<tr><th scope=row>Albertson College</th><td>Yes</td><td>  587</td><td>  479</td><td> 158</td><td>38</td><td>62</td><td>  678</td><td>  41</td><td>13500</td><td>3335</td><td>500</td><td> 675</td><td>67</td><td> 73</td><td> 9.4</td><td>11</td><td> 9727</td><td> 55</td></tr>
	<tr><th scope=row>Albertus Magnus College</th><td>Yes</td><td>  353</td><td>  340</td><td> 103</td><td>17</td><td>45</td><td>  416</td><td> 230</td><td>13290</td><td>5720</td><td>500</td><td>1500</td><td>90</td><td> 93</td><td>11.5</td><td>26</td><td> 8861</td><td> 63</td></tr>
	<tr><th scope=row>Albion College</th><td>Yes</td><td> 1899</td><td> 1720</td><td> 489</td><td>37</td><td>68</td><td> 1594</td><td>  32</td><td>13868</td><td>4826</td><td>450</td><td> 850</td><td>89</td><td>100</td><td>13.7</td><td>37</td><td>11487</td><td> 73</td></tr>
	<tr><th scope=row>Albright College</th><td>Yes</td><td> 1038</td><td>  839</td><td> 227</td><td>30</td><td>63</td><td>  973</td><td> 306</td><td>15595</td><td>4400</td><td>300</td><td> 500</td><td>79</td><td> 84</td><td>11.3</td><td>23</td><td>11644</td><td> 80</td></tr>
	<tr><th scope=row>Alderson-Broaddus College</th><td>Yes</td><td>  582</td><td>  498</td><td> 172</td><td>21</td><td>44</td><td>  799</td><td>  78</td><td>10468</td><td>3380</td><td>660</td><td>1800</td><td>40</td><td> 41</td><td>11.5</td><td>15</td><td> 8991</td><td> 52</td></tr>
	<tr><th scope=row>Alfred University</th><td>Yes</td><td> 1732</td><td> 1425</td><td> 472</td><td>37</td><td>75</td><td> 1830</td><td> 110</td><td>16548</td><td>5406</td><td>500</td><td> 600</td><td>82</td><td> 88</td><td>11.3</td><td>31</td><td>10932</td><td> 73</td></tr>
	<tr><th scope=row>Allegheny College</th><td>Yes</td><td> 2652</td><td> 1900</td><td> 484</td><td>44</td><td>77</td><td> 1707</td><td>  44</td><td>17080</td><td>4440</td><td>400</td><td> 600</td><td>73</td><td> 91</td><td> 9.9</td><td>41</td><td>11711</td><td> 76</td></tr>
	<tr><th scope=row>Allentown Coll. of St. Francis de Sales</th><td>Yes</td><td> 1179</td><td>  780</td><td> 290</td><td>38</td><td>64</td><td> 1130</td><td> 638</td><td> 9690</td><td>4785</td><td>600</td><td>1000</td><td>60</td><td> 84</td><td>13.3</td><td>21</td><td> 7940</td><td> 74</td></tr>
	<tr><th scope=row>Alma College</th><td>Yes</td><td> 1267</td><td> 1080</td><td> 385</td><td>44</td><td>73</td><td> 1306</td><td>  28</td><td>12572</td><td>4552</td><td>400</td><td> 400</td><td>79</td><td> 87</td><td>15.3</td><td>32</td><td> 9305</td><td> 68</td></tr>
	<tr><th scope=row>Alverno College</th><td>Yes</td><td>  494</td><td>  313</td><td> 157</td><td>23</td><td>46</td><td> 1317</td><td>1235</td><td> 8352</td><td>3640</td><td>650</td><td>2449</td><td>36</td><td> 69</td><td>11.1</td><td>26</td><td> 8127</td><td> 55</td></tr>
	<tr><th scope=row>American International College</th><td>Yes</td><td> 1420</td><td> 1093</td><td> 220</td><td> 9</td><td>22</td><td> 1018</td><td> 287</td><td> 8700</td><td>4780</td><td>450</td><td>1400</td><td>78</td><td> 84</td><td>14.7</td><td>19</td><td> 7355</td><td> 69</td></tr>
	<tr><th scope=row>Amherst College</th><td>Yes</td><td> 4302</td><td>  992</td><td> 418</td><td>83</td><td>96</td><td> 1593</td><td>   5</td><td>19760</td><td>5300</td><td>660</td><td>1598</td><td>93</td><td> 98</td><td> 8.4</td><td>63</td><td>21424</td><td>100</td></tr>
	<tr><th scope=row>Anderson University</th><td>Yes</td><td> 1216</td><td>  908</td><td> 423</td><td>19</td><td>40</td><td> 1819</td><td> 281</td><td>10100</td><td>3520</td><td>550</td><td>1100</td><td>48</td><td> 61</td><td>12.1</td><td>14</td><td> 7994</td><td> 59</td></tr>
	<tr><th scope=row>Andrews University</th><td>Yes</td><td> 1130</td><td>  704</td><td> 322</td><td>14</td><td>23</td><td> 1586</td><td> 326</td><td> 9996</td><td>3090</td><td>900</td><td>1320</td><td>62</td><td> 66</td><td>11.5</td><td>18</td><td>10908</td><td> 46</td></tr>
	<tr><th scope=row>Angelo State University</th><td>No </td><td> 3540</td><td> 2001</td><td>1016</td><td>24</td><td>54</td><td> 4190</td><td>1512</td><td> 5130</td><td>3592</td><td>500</td><td>2000</td><td>60</td><td> 62</td><td>23.1</td><td> 5</td><td> 4010</td><td> 34</td></tr>
	<tr><th scope=row>Antioch University</th><td>Yes</td><td>  713</td><td>  661</td><td> 252</td><td>25</td><td>44</td><td>  712</td><td>  23</td><td>15476</td><td>3336</td><td>400</td><td>1100</td><td>69</td><td> 82</td><td>11.3</td><td>35</td><td>42926</td><td> 48</td></tr>
	<tr><th scope=row>Appalachian State University</th><td>No </td><td> 7313</td><td> 4664</td><td>1910</td><td>20</td><td>63</td><td> 9940</td><td>1035</td><td> 6806</td><td>2540</td><td> 96</td><td>2000</td><td>83</td><td> 96</td><td>18.3</td><td>14</td><td> 5854</td><td> 70</td></tr>
	<tr><th scope=row>Aquinas College</th><td>Yes</td><td>  619</td><td>  516</td><td> 219</td><td>20</td><td>51</td><td> 1251</td><td> 767</td><td>11208</td><td>4124</td><td>350</td><td>1615</td><td>55</td><td> 65</td><td>12.7</td><td>25</td><td> 6584</td><td> 65</td></tr>
	<tr><th scope=row>Arizona State University Main campus</th><td>No </td><td>12809</td><td>10308</td><td>3761</td><td>24</td><td>49</td><td>22593</td><td>7585</td><td> 7434</td><td>4850</td><td>700</td><td>2100</td><td>88</td><td> 93</td><td>18.9</td><td> 5</td><td> 4602</td><td> 48</td></tr>
	<tr><th scope=row>Arkansas College (Lyon College)</th><td>Yes</td><td>  708</td><td>  334</td><td> 166</td><td>46</td><td>74</td><td>  530</td><td> 182</td><td> 8644</td><td>3922</td><td>500</td><td> 800</td><td>79</td><td> 88</td><td>12.6</td><td>24</td><td>14579</td><td> 54</td></tr>
	<tr><th scope=row>Arkansas Tech University</th><td>No </td><td> 1734</td><td> 1729</td><td> 951</td><td>12</td><td>52</td><td> 3602</td><td> 939</td><td> 3460</td><td>2650</td><td>450</td><td>1000</td><td>57</td><td> 60</td><td>19.6</td><td> 5</td><td> 4739</td><td> 48</td></tr>
	<tr><th scope=row>Assumption College</th><td>Yes</td><td> 2135</td><td> 1700</td><td> 491</td><td>23</td><td>59</td><td> 1708</td><td> 689</td><td>12000</td><td>5920</td><td>500</td><td> 500</td><td>93</td><td> 93</td><td>13.8</td><td>30</td><td> 7100</td><td> 88</td></tr>
	<tr><th scope=row>Auburn University-Main Campus</th><td>No </td><td> 7548</td><td> 6791</td><td>3070</td><td>25</td><td>57</td><td>16262</td><td>1716</td><td> 6300</td><td>3933</td><td>600</td><td>1908</td><td>85</td><td> 91</td><td>16.7</td><td>18</td><td> 6642</td><td> 69</td></tr>
	<tr><th scope=row>Augsburg College</th><td>Yes</td><td>  662</td><td>  513</td><td> 257</td><td>12</td><td>30</td><td> 2074</td><td> 726</td><td>11902</td><td>4372</td><td>540</td><td> 950</td><td>65</td><td> 65</td><td>12.8</td><td>31</td><td> 7836</td><td> 58</td></tr>
	<tr><th scope=row>Augustana College IL</th><td>Yes</td><td> 1879</td><td> 1658</td><td> 497</td><td>36</td><td>69</td><td> 1950</td><td>  38</td><td>13353</td><td>4173</td><td>540</td><td> 821</td><td>78</td><td> 83</td><td>12.7</td><td>40</td><td> 9220</td><td> 71</td></tr>
	<tr><th scope=row>⋮</th><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td><td>⋮</td></tr>
	<tr><th scope=row>Westfield State College</th><td>No </td><td> 3100</td><td>2150</td><td> 825</td><td> 3</td><td>20</td><td>3234</td><td> 941</td><td> 5542</td><td>3788</td><td>500</td><td>1300</td><td>75</td><td>79</td><td>15.7</td><td>20</td><td> 4222</td><td>65</td></tr>
	<tr><th scope=row>Westminster College MO</th><td>Yes</td><td>  662</td><td> 553</td><td> 184</td><td>20</td><td>43</td><td> 665</td><td>  37</td><td>10720</td><td>4050</td><td>600</td><td>1650</td><td>66</td><td>70</td><td>12.5</td><td>20</td><td> 7925</td><td>62</td></tr>
	<tr><th scope=row>Westminster College</th><td>Yes</td><td>  996</td><td> 866</td><td> 377</td><td>29</td><td>58</td><td>1411</td><td>  72</td><td>12065</td><td>3615</td><td>430</td><td> 685</td><td>62</td><td>78</td><td>12.5</td><td>41</td><td> 8596</td><td>80</td></tr>
	<tr><th scope=row>Westminster College of Salt Lake City</th><td>Yes</td><td>  917</td><td> 720</td><td> 213</td><td>21</td><td>60</td><td> 979</td><td> 743</td><td> 8820</td><td>4050</td><td>600</td><td>2025</td><td>68</td><td>83</td><td>10.5</td><td>34</td><td> 7170</td><td>50</td></tr>
	<tr><th scope=row>Westmont College</th><td>No </td><td>  950</td><td> 713</td><td> 351</td><td>42</td><td>72</td><td>1276</td><td>   9</td><td>14320</td><td>5304</td><td>490</td><td>1410</td><td>77</td><td>77</td><td>14.9</td><td>17</td><td> 8837</td><td>87</td></tr>
	<tr><th scope=row>Wheaton College IL</th><td>Yes</td><td> 1432</td><td> 920</td><td> 548</td><td>56</td><td>84</td><td>2200</td><td>  56</td><td>11480</td><td>4200</td><td>530</td><td>1400</td><td>81</td><td>83</td><td>12.7</td><td>40</td><td>11916</td><td>85</td></tr>
	<tr><th scope=row>Westminster College PA</th><td>Yes</td><td> 1738</td><td>1373</td><td> 417</td><td>21</td><td>55</td><td>1335</td><td>  30</td><td>18460</td><td>5970</td><td>700</td><td> 850</td><td>92</td><td>96</td><td>13.2</td><td>41</td><td>22704</td><td>71</td></tr>
	<tr><th scope=row>Wheeling Jesuit College</th><td>Yes</td><td>  903</td><td> 755</td><td> 213</td><td>15</td><td>49</td><td> 971</td><td> 305</td><td>10500</td><td>4545</td><td>600</td><td> 600</td><td>66</td><td>71</td><td>14.1</td><td>27</td><td> 7494</td><td>72</td></tr>
	<tr><th scope=row>Whitman College</th><td>Yes</td><td> 1861</td><td> 998</td><td> 359</td><td>45</td><td>77</td><td>1220</td><td>  46</td><td>16670</td><td>4900</td><td>750</td><td> 800</td><td>80</td><td>83</td><td>10.5</td><td>51</td><td>13198</td><td>72</td></tr>
	<tr><th scope=row>Whittier College</th><td>Yes</td><td> 1681</td><td>1069</td><td> 344</td><td>35</td><td>63</td><td>1235</td><td>  30</td><td>16249</td><td>5699</td><td>500</td><td>1998</td><td>84</td><td>92</td><td>13.6</td><td>29</td><td>11778</td><td>52</td></tr>
	<tr><th scope=row>Whitworth College</th><td>Yes</td><td> 1121</td><td> 926</td><td> 372</td><td>43</td><td>70</td><td>1270</td><td> 160</td><td>12660</td><td>4500</td><td>678</td><td>2424</td><td>80</td><td>80</td><td>16.9</td><td>20</td><td> 8328</td><td>80</td></tr>
	<tr><th scope=row>Widener University</th><td>Yes</td><td> 2139</td><td>1492</td><td> 502</td><td>24</td><td>64</td><td>2186</td><td>2171</td><td>12350</td><td>5370</td><td>500</td><td>1350</td><td>88</td><td>86</td><td>12.6</td><td>19</td><td> 9603</td><td>63</td></tr>
	<tr><th scope=row>Wilkes University</th><td>Yes</td><td> 1631</td><td>1431</td><td> 434</td><td>15</td><td>36</td><td>1803</td><td> 603</td><td>11150</td><td>5130</td><td>550</td><td>1260</td><td>78</td><td>92</td><td>13.3</td><td>24</td><td> 8543</td><td>67</td></tr>
	<tr><th scope=row>Willamette University</th><td>Yes</td><td> 1658</td><td>1327</td><td> 395</td><td>49</td><td>80</td><td>1595</td><td> 159</td><td>14800</td><td>4620</td><td>400</td><td> 790</td><td>91</td><td>94</td><td>13.3</td><td>37</td><td>10779</td><td>68</td></tr>
	<tr><th scope=row>William Jewell College</th><td>Yes</td><td>  663</td><td> 547</td><td> 315</td><td>32</td><td>67</td><td>1279</td><td>  75</td><td>10060</td><td>2970</td><td>500</td><td>2600</td><td>74</td><td>80</td><td>11.2</td><td>19</td><td> 7885</td><td>59</td></tr>
	<tr><th scope=row>William Woods University</th><td>Yes</td><td>  469</td><td> 435</td><td> 227</td><td>17</td><td>39</td><td> 851</td><td> 120</td><td>10535</td><td>4365</td><td>550</td><td>3700</td><td>39</td><td>66</td><td>12.9</td><td>16</td><td> 7438</td><td>52</td></tr>
	<tr><th scope=row>Williams College</th><td>Yes</td><td> 4186</td><td>1245</td><td> 526</td><td>81</td><td>96</td><td>1988</td><td>  29</td><td>19629</td><td>5790</td><td>500</td><td>1200</td><td>94</td><td>99</td><td> 9.0</td><td>64</td><td>22014</td><td>99</td></tr>
	<tr><th scope=row>Wilson College</th><td>Yes</td><td>  167</td><td> 130</td><td>  46</td><td>16</td><td>50</td><td> 199</td><td> 676</td><td>11428</td><td>5084</td><td>450</td><td> 475</td><td>67</td><td>76</td><td> 8.3</td><td>43</td><td>10291</td><td>67</td></tr>
	<tr><th scope=row>Wingate College</th><td>Yes</td><td> 1239</td><td>1017</td><td> 383</td><td>10</td><td>34</td><td>1207</td><td> 157</td><td> 7820</td><td>3400</td><td>550</td><td>1550</td><td>69</td><td>81</td><td>13.9</td><td> 8</td><td> 7264</td><td>91</td></tr>
	<tr><th scope=row>Winona State University</th><td>No </td><td> 3325</td><td>2047</td><td>1301</td><td>20</td><td>45</td><td>5800</td><td> 872</td><td> 4200</td><td>2700</td><td>300</td><td>1200</td><td>53</td><td>60</td><td>20.2</td><td>18</td><td> 5318</td><td>58</td></tr>
	<tr><th scope=row>Winthrop University</th><td>No </td><td> 2320</td><td>1805</td><td> 769</td><td>24</td><td>61</td><td>3395</td><td> 670</td><td> 6400</td><td>3392</td><td>580</td><td>2150</td><td>71</td><td>80</td><td>12.8</td><td>26</td><td> 6729</td><td>59</td></tr>
	<tr><th scope=row>Wisconsin Lutheran College</th><td>Yes</td><td>  152</td><td> 128</td><td>  75</td><td>17</td><td>41</td><td> 282</td><td>  22</td><td> 9100</td><td>3700</td><td>500</td><td>1400</td><td>48</td><td>48</td><td> 8.5</td><td>26</td><td> 8960</td><td>50</td></tr>
	<tr><th scope=row>Wittenberg University</th><td>Yes</td><td> 1979</td><td>1739</td><td> 575</td><td>42</td><td>68</td><td>1980</td><td> 144</td><td>15948</td><td>4404</td><td>400</td><td> 800</td><td>82</td><td>95</td><td>12.8</td><td>29</td><td>10414</td><td>78</td></tr>
	<tr><th scope=row>Wofford College</th><td>Yes</td><td> 1501</td><td> 935</td><td> 273</td><td>51</td><td>83</td><td>1059</td><td>  34</td><td>12680</td><td>4150</td><td>605</td><td>1440</td><td>91</td><td>92</td><td>15.3</td><td>42</td><td> 7875</td><td>75</td></tr>
	<tr><th scope=row>Worcester Polytechnic Institute</th><td>Yes</td><td> 2768</td><td>2314</td><td> 682</td><td>49</td><td>86</td><td>2802</td><td>  86</td><td>15884</td><td>5370</td><td>530</td><td> 730</td><td>92</td><td>94</td><td>15.2</td><td>34</td><td>10774</td><td>82</td></tr>
	<tr><th scope=row>Worcester State College</th><td>No </td><td> 2197</td><td>1515</td><td> 543</td><td> 4</td><td>26</td><td>3089</td><td>2029</td><td> 6797</td><td>3900</td><td>500</td><td>1200</td><td>60</td><td>60</td><td>21.0</td><td>14</td><td> 4469</td><td>40</td></tr>
	<tr><th scope=row>Xavier University</th><td>Yes</td><td> 1959</td><td>1805</td><td> 695</td><td>24</td><td>47</td><td>2849</td><td>1107</td><td>11520</td><td>4960</td><td>600</td><td>1250</td><td>73</td><td>75</td><td>13.3</td><td>31</td><td> 9189</td><td>83</td></tr>
	<tr><th scope=row>Xavier University of Louisiana</th><td>Yes</td><td> 2097</td><td>1915</td><td> 695</td><td>34</td><td>61</td><td>2793</td><td> 166</td><td> 6900</td><td>4200</td><td>617</td><td> 781</td><td>67</td><td>75</td><td>14.4</td><td>20</td><td> 8323</td><td>49</td></tr>
	<tr><th scope=row>Yale University</th><td>Yes</td><td>10705</td><td>2453</td><td>1317</td><td>95</td><td>99</td><td>5217</td><td>  83</td><td>19840</td><td>6510</td><td>630</td><td>2115</td><td>96</td><td>96</td><td> 5.8</td><td>49</td><td>40386</td><td>99</td></tr>
	<tr><th scope=row>York College of Pennsylvania</th><td>Yes</td><td> 2989</td><td>1855</td><td> 691</td><td>28</td><td>63</td><td>2988</td><td>1726</td><td> 4990</td><td>3560</td><td>500</td><td>1250</td><td>75</td><td>75</td><td>18.1</td><td>28</td><td> 4509</td><td>99</td></tr>
</tbody>
</table>



## 2. We get the numerical summaries of the variables in the data set.


```R
summary(college)
```


       Private               Apps           Accept          Enroll    
     Length:777         Min.   :   81   Min.   :   72   Min.   :  35  
     Class :character   1st Qu.:  776   1st Qu.:  604   1st Qu.: 242  
     Mode  :character   Median : 1558   Median : 1110   Median : 434  
                        Mean   : 3002   Mean   : 2019   Mean   : 780  
                        3rd Qu.: 3624   3rd Qu.: 2424   3rd Qu.: 902  
                        Max.   :48094   Max.   :26330   Max.   :6392  
       Top10perc       Top25perc      F.Undergrad     P.Undergrad     
     Min.   : 1.00   Min.   :  9.0   Min.   :  139   Min.   :    1.0  
     1st Qu.:15.00   1st Qu.: 41.0   1st Qu.:  992   1st Qu.:   95.0  
     Median :23.00   Median : 54.0   Median : 1707   Median :  353.0  
     Mean   :27.56   Mean   : 55.8   Mean   : 3700   Mean   :  855.3  
     3rd Qu.:35.00   3rd Qu.: 69.0   3rd Qu.: 4005   3rd Qu.:  967.0  
     Max.   :96.00   Max.   :100.0   Max.   :31643   Max.   :21836.0  
        Outstate       Room.Board       Books           Personal   
     Min.   : 2340   Min.   :1780   Min.   :  96.0   Min.   : 250  
     1st Qu.: 7320   1st Qu.:3597   1st Qu.: 470.0   1st Qu.: 850  
     Median : 9990   Median :4200   Median : 500.0   Median :1200  
     Mean   :10441   Mean   :4358   Mean   : 549.4   Mean   :1341  
     3rd Qu.:12925   3rd Qu.:5050   3rd Qu.: 600.0   3rd Qu.:1700  
     Max.   :21700   Max.   :8124   Max.   :2340.0   Max.   :6800  
          PhD            Terminal       S.F.Ratio      perc.alumni   
     Min.   :  8.00   Min.   : 24.0   Min.   : 2.50   Min.   : 0.00  
     1st Qu.: 62.00   1st Qu.: 71.0   1st Qu.:11.50   1st Qu.:13.00  
     Median : 75.00   Median : 82.0   Median :13.60   Median :21.00  
     Mean   : 72.66   Mean   : 79.7   Mean   :14.09   Mean   :22.74  
     3rd Qu.: 85.00   3rd Qu.: 92.0   3rd Qu.:16.50   3rd Qu.:31.00  
     Max.   :103.00   Max.   :100.0   Max.   :39.80   Max.   :64.00  
         Expend        Grad.Rate     
     Min.   : 3186   Min.   : 10.00  
     1st Qu.: 6751   1st Qu.: 53.00  
     Median : 8377   Median : 65.00  
     Mean   : 9660   Mean   : 65.46  
     3rd Qu.:10830   3rd Qu.: 78.00  
     Max.   :56233   Max.   :118.00  


## 3. We produce pairs plot to generate an overall insight from the data set visually.  
It can be done for the first ten columns only.


```R
college[,1] = as.factor(factor(college[,1]))

pairs(college[, 1:10])
```


![output_8_0](https://user-images.githubusercontent.com/82738676/181878608-b536a554-35f7-436d-ace3-f7f3b2d56d92.png)





## 4. We produce side-by-side boxplots of **Outstate** versus **Private** columns.


```R
# Create a boxplot of Outstate versus Private
boxplot(Outstate ~ Private, data = college)
```


    
![output_10_0](https://user-images.githubusercontent.com/82738676/181878616-20fa733f-7d69-4e12-9639-9c2b72d8e3bb.png)



Create a new qualitative variable, called Elite, by binning the Top10perc variable. We are going to divide universities
into two groups based on whether or not the proportion of students coming from the top 10% of their high school classes exceeds 50 %.


```R
# Create a new variable column Elite where the top10perc of newly accepted students reaches more than 50. Set this to Yes and factorize
Elite <- rep("No", nrow(college))
Elite[college$Top10perc > 50] <- "Yes"
Elite <- as.factor(Elite)
college <- data.frame(college , Elite)

# Print the summary of the data set
summary(college)
```


     Private        Apps           Accept          Enroll       Top10perc    
     No :212   Min.   :   81   Min.   :   72   Min.   :  35   Min.   : 1.00  
     Yes:565   1st Qu.:  776   1st Qu.:  604   1st Qu.: 242   1st Qu.:15.00  
               Median : 1558   Median : 1110   Median : 434   Median :23.00  
               Mean   : 3002   Mean   : 2019   Mean   : 780   Mean   :27.56  
               3rd Qu.: 3624   3rd Qu.: 2424   3rd Qu.: 902   3rd Qu.:35.00  
               Max.   :48094   Max.   :26330   Max.   :6392   Max.   :96.00  
       Top25perc      F.Undergrad     P.Undergrad         Outstate    
     Min.   :  9.0   Min.   :  139   Min.   :    1.0   Min.   : 2340  
     1st Qu.: 41.0   1st Qu.:  992   1st Qu.:   95.0   1st Qu.: 7320  
     Median : 54.0   Median : 1707   Median :  353.0   Median : 9990  
     Mean   : 55.8   Mean   : 3700   Mean   :  855.3   Mean   :10441  
     3rd Qu.: 69.0   3rd Qu.: 4005   3rd Qu.:  967.0   3rd Qu.:12925  
     Max.   :100.0   Max.   :31643   Max.   :21836.0   Max.   :21700  
       Room.Board       Books           Personal         PhD        
     Min.   :1780   Min.   :  96.0   Min.   : 250   Min.   :  8.00  
     1st Qu.:3597   1st Qu.: 470.0   1st Qu.: 850   1st Qu.: 62.00  
     Median :4200   Median : 500.0   Median :1200   Median : 75.00  
     Mean   :4358   Mean   : 549.4   Mean   :1341   Mean   : 72.66  
     3rd Qu.:5050   3rd Qu.: 600.0   3rd Qu.:1700   3rd Qu.: 85.00  
     Max.   :8124   Max.   :2340.0   Max.   :6800   Max.   :103.00  
        Terminal       S.F.Ratio      perc.alumni        Expend     
     Min.   : 24.0   Min.   : 2.50   Min.   : 0.00   Min.   : 3186  
     1st Qu.: 71.0   1st Qu.:11.50   1st Qu.:13.00   1st Qu.: 6751  
     Median : 82.0   Median :13.60   Median :21.00   Median : 8377  
     Mean   : 79.7   Mean   :14.09   Mean   :22.74   Mean   : 9660  
     3rd Qu.: 92.0   3rd Qu.:16.50   3rd Qu.:31.00   3rd Qu.:10830  
     Max.   :100.0   Max.   :39.80   Max.   :64.00   Max.   :56233  
       Grad.Rate      Elite    
     Min.   : 10.00   No :699  
     1st Qu.: 53.00   Yes: 78  
     Median : 65.00            
     Mean   : 65.46            
     3rd Qu.: 78.00            
     Max.   :118.00            



```R
# Create a 2 by 2 plots
par(mfrow = c(2, 2))

# Analyze four of the columns in the dataset by using the histogram function
hist(college$Apps, xlab = "Number of Applicants", main  = "")
hist(college$Accept, breaks = 12, xlab = "Number of Acceptance", main  = "")
hist(college$Grad.Rate, xlab = "Graduation Rate", main = "")
hist(college$Personal, breaks = 12, xlab = "Expected Personal Spending", main = "")
```


![output_13_0](https://user-images.githubusercontent.com/82738676/181878619-9c98ab51-a43a-4978-acf9-e94604e10c21.png)

    


## 5. By exploring the data, I have come up with different questions:

- What are the top 10 universities and colleges with the highest number of new students from top  10% of high school class?  

> **Masschusetts Institute of Technology** is at the top with students belonging to their top 10% class in high school. Following schools are **Harvey Mudd College, University of California Berkeley, Yale University, Duke University, Harvard University, Princeton University, Georgia Insitute of Technology, Brown University, and Dartmouth college**. However, this does not necessarily guarantees that these schools are the best 10 schools in United States.


```R
# Subset the top 10 universities and college by order
top10 = college[order(college$Top10perc, decreasing = TRUE), ]

# Print the univerisities or college
head(row.names(top10), 10)
```


<style>
.list-inline {list-style: none; margin:0; padding: 0}
.list-inline>li {display: inline-block}
.list-inline>li:not(:last-child)::after {content: "\00b7"; padding: 0 .5ex}
</style>
<ol class=list-inline><li>'Massachusetts Institute of Technology'</li><li>'Harvey Mudd College'</li><li>'University of California at Berkeley'</li><li>'Yale University'</li><li>'Duke University'</li><li>'Harvard University'</li><li>'Princeton University'</li><li>'Georgia Institute of Technology'</li><li>'Brown University'</li><li>'Dartmouth College'</li></ol>



- What are thetop 10 universities and colleges with the lowest rate of accepted students?  

> **Princeton University** is at the top with students belonging to their top 10% class in high school. Following schools are **Harvard University, Yale University, Amherst College, Brown University, Georgetown University, Dartmouth College, Duke University, Columbia University, and Williams College**. However, this does not necessarily guarantees that these schools are the best 10 schools in United States.


```R
# Get the acceptance rate column by dividing the number of accepted students to the number of applicants
college$accept_rate = college$Accept / college$Apps

# Subset
top10lwst = college[order(college$accept_rate, decreasing = FALSE), ]
head(row.names(top10lwst), 10)
```


<style>
.list-inline {list-style: none; margin:0; padding: 0}
.list-inline>li {display: inline-block}
.list-inline>li:not(:last-child)::after {content: "\00b7"; padding: 0 .5ex}
</style>
<ol class=list-inline><li>'Princeton University'</li><li>'Harvard University'</li><li>'Yale University'</li><li>'Amherst College'</li><li>'Brown University'</li><li>'Georgetown University'</li><li>'Dartmouth College'</li><li>'Duke University'</li><li>'Columbia University'</li><li>'Williams College'</li></ol>



- What are thetop 10 universities and colleges with the highest rate of accepted students?  

> **Emporia State Univeristy** is at the top with students belonging to their top 10% class in high school. Following schools are **Mayville State University, MidAmerica Nazarene College, Southwest Baptist University, University of Wisconsin-Superior, Wayne State College, Arkansas Tech University, Southwestern Adventist College, Pikeville College, and Mount Marty College**. However, this does not necessarily guarantees that these schools are the best 10 schools in United States.


```R
# Get the acceptance rate column by dividing the number of accepted students to the number of applicants
college$accept_rate = college$Accept / college$Apps

# Subset
top10lwst = college[order(college$accept_rate, decreasing = TRUE), ]
head(row.names(top10lwst), 10)
```


<style>
.list-inline {list-style: none; margin:0; padding: 0}
.list-inline>li {display: inline-block}
.list-inline>li:not(:last-child)::after {content: "\00b7"; padding: 0 .5ex}
</style>
<ol class=list-inline><li>'Emporia State University'</li><li>'Mayville State University'</li><li>'MidAmerica Nazarene College'</li><li>'Southwest Baptist University'</li><li>'University of Wisconsin-Superior'</li><li>'Wayne State College'</li><li>'Arkansas Tech University'</li><li>'Southwestern Adventist College'</li><li>'Pikeville College'</li><li>'Mount Marty College'</li></ol>



- What is the top univeristy or college with the highest number of enrolment?  

> Rutgers at New Brunswick


```R
# Get the college or university with the highest number of applications received
row.names(college)[which.max(college$Apps)]
```


'Rutgers at New Brunswick'


We get the relationship of Outstate tuition and the Graduation Rate. The figure shows that the higher the outstate tuition, the higher the rate of graduation. However, it does not necessarily guarantees correlation nor causation.


```R
plot(Grad.Rate ~ Outstate, data = college)
```


    
![output_24_0](https://user-images.githubusercontent.com/82738676/181878627-64915b1c-342f-4bb4-99b1-29c5229f3461.png)


