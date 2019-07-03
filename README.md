author: David Shorten <dpshorten@gmail.com>

Instructions:

1.) Install CaImAn as per the instructions on github. We were using the June 11 2019 commit<br/>
(https://github.com/flatironinstitute/CaImAn/commit/c26be44cafc61c3fc5d77434ad0fce5f6efc9cac)<br/>

3.) Find where CaImAn is installed on your system. In the file caiman/source_extraction/cnmf/estimates.py<br/>
Insert the following line on line 512 (after the line "mov = caiman.concatenate(...")<br/>

mov.save("foo" + str(frame_range[0]) + ".tif")<br/>

2.) Run the file demo_caiman_basic2.py. I'm not sure whether or not it has to be inside the<br/>
demos/general/ directory.<br/>

This file is an edited version of the original demo_caiman_basic.py<br/>

The changes that have been made are as follows:<br/>

1.) A few parameters<br/>
2.) file names<br/>
3.) Turning off the use of the CNN classifier<br/>
4.) Calling the function detrend_df_f() to normalise the fluorescence values<br/>
5.) Duming the resulting df_f values into a pickle file<br/>
6.) Calling nb_view_components which (if I remember correctly) is what lets you view<br/>
the results in a browser.<br/>
7.) Changed the play_movie call such that it was called multiple times on fewer frames<br/>
    to prevent crashes due to lack of memory.<br/>


Tips:<br/>

If you find that you are running out of memory, consider:<br/>
1.) Reducing K<br/>
3.) Decreasing rf (although this will incur a time penalty)<br/>
4.) Dividing your recordings into smaller files<br/>