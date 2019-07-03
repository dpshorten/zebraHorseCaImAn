author: David Shorten <dpshorten@gmail.com>

Instructions:

1.) Install CaImAn as per the instructions on github. We were using the June 11 2019 commit\
(https://github.com/flatironinstitute/CaImAn/commit/c26be44cafc61c3fc5d77434ad0fce5f6efc9cac)\

3.) Find where CaImAn is installed on your system. In the file caiman/source_extraction/cnmf/estimates.py\
Insert the following line on line 512 (after the line "mov = caiman.concatenate(...")\

mov.save("foo" + str(frame_range[0]) + ".tif")\

2.) Run the file demo_caiman_basic2.py. I'm not sure whether or not it has to be inside the\
demos/general/ directory.\

This file is an edited version of the original demo_caiman_basic.py\

The changes that have been made are as follows:\

1.) A few parameters\
2.) file names\
3.) Turning off the use of the CNN classifier\
4.) Calling the function detrend_df_f() to normalise the fluorescence values\
5.) Duming the resulting df_f values into a pickle file\
6.) Calling nb_view_components which (if I remember correctly) is what lets you view\
the results in a browser.\
7.) Changed the play_movie call such that it was called multiple times on fewer frames\
    to prevent crashes due to lack of memory.\


Tips:\

If you find that you are running out of memory, consider:\
1.) Reducing K\
3.) Decreasing rf (although this will incur a time penalty)\
4.) Dividing your recordings into smaller files\