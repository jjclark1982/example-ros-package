^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Changelog for package jsk_travis
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

0.2.0 (2015-11-24)
------------------
* writing result to wrong place seems to be solved? (`#193
  <https://github.com/jsk-ros-pkg/jsk_travis/issues/193>`_ ) Do not `rm *MISSING` before catkin_test_results
* Contributors: Kei Okada

0.1.7 (2015-11-22)
------------------
* more quiet for 4M limit `#194 <https://github.com/jsk-ros-pkg/jsk_travis/pull/194>`_

  * travis.sh: be quiet when source setup.bash
  * travis.sh: apt-get update with -q
  * travis.sh: pip install with -q

* Describe about USE_DEB=source for `#180 <https://github.com/jsk-ros-pkg/jsk_travis/issues/180>`_
* Contributors: Kei Okada, Kentaro Wada

0.1.6 (2015-11-03)
------------------
* travis.sh: `#180 <https://github.com/jsk-ros-pkg/jsk_travis/issues/180>`_ is NG, USE_DEB can have true, false and source
* Revert "rosws init . is already done at https://github.com/jsk-ros-pkg/jsk_travis/blob/master/travis.sh#L117"
* fix typo on README.md
* Contributors: Kei Okada

0.1.5 (2015-11-03)
------------------
* rosws init . is already done at https://github.com/jsk-ros-pkg/jsk_travis/blob/master/travis.sh#L117
* Contributors: Kei Okada

0.1.4 (2015-11-02)
------------------
* [travis.sh] check including empty string
* check if test_pgks is " " this causes catkin run_tests --no-deps without any target name
* Run tests verbosely & interactively with -iv
* Contributors: Kei Okada, Kentaro Wada

0.1.3 (2015-10-29)
------------------
* [travis.sh][check_metapackage.py] use parser for detecting metapackage
* use .travis.rosinstall when USE_DEB != true
  - refactor `if` condition
  - use `.travis.rosinstall` when `USE_DEB != true` (before this PR, `.travis.rosinstall` is not used when `USE_DEB = source`)
* Warn about special chars in BEFORE_SCRIPT closes `#171 <https://github.com/jsk-ros-pkg/jsk_travis/issues/171>`_
* Add document about CATKIN_PARALLEL_TEST_JOBS
* Contributors: Yuki Furuta, Kentaro Wada, Ryohei Ueda

0.1.2 (2015-10-19)
------------------
* Check version of ros tools
* Run rostest again with --text option if the test failed  Closes `#165 <https://github.com/jsk-ros-pkg/jsk_travis/issues/165>`_
* Describe about debugging with change on jsk_travis
* typo in README
* No need wstool rm about self repo
* Run `rospack profile` to update rospack cache before test
* Highlight test start and end with >>> & <<<<
* Source devel/setup.bash before run test to update ROS_PACKAGE_PATH for  rostest
* Describe about where test runs
* Summarize result of catkin build with --summarize option  For https://github.com/jsk-ros-pkg/jsk_travis/issues/159
* env USE_TRAVIS to force test run test on travis
* Comment about container-based travis env
* [README.md] add documents to how to release package
* Contributors: Kei Okada, Kentaro Wada, Ryohei Ueda

0.1.1 (2015-09-27)
------------------
* [API Break] config file name has been changed from .rosinstall to .travis.rosinstall

  * [travis.sh] Avoid error when nothing to remove in .travis.rosinstall
  * [travis.sh] Install from source with .travis.rosinstall.$ROS_DISTRO
  * [travis.sh] Rename source dependency filename .rosinstall -> .travis.rosinstall Closes #133

* add documents

  * [README] Add document about how to setup jsk_travis and .travis
  * [REAMDE] Add document about BEFORE_SCRIPT and EXTRA_DEB
  * [README] Add documentation about BUILD_PKGS
  * [README] Describe about USE_DEB and .travis.rosinstall
  * [README] prettify
  * [README] Add document about ROS_DISTRO
  * [README] Add document about USE_JENKINS and NO_SUDO

* [travis.sh] Need to upgrade pip for Ubuntu 12.04 For https://github.com/jsk-ros-pkg/jsk_demos/pull/1065
* [travis.sh] Remove NO_SUDO: pip is already installed on travis
* [travis.sh] Add version check of pip and rosdep
* [travis.sh] Fixed the bug of wstool to resolve depends
* [travis.sh] Use `--no-deps` to limit packages to tests
* [travis.sh] Check wstool version before using it
* [travis.sh] Refactor: robuster regex match and use wstool rm not comment out
* [travis_jenkins] Try git clone until success on jenkins
* [travis.sh] Added Gitter badge
* Contributors: Kentaro Wada, Ryohei Ueda, The Gitter Badger

0.1.0 (2015-08-28)
------------------
* catkin is now 2.0+ http://packages.ros.org/ros/ubuntu/pool/main/p/python-catkin-tools/
* travis.sh add ~/.ros/test_results/
* Install python-jenkins user-locally instead of install via sudo and add
  NO_SUDO environmental variable to skip apt-get
* add slack notifications
* [travis.sh] Correct run_tests result using catkin_test_results (*THIS ONLY FOR HYDRO, previously hydro pass test even if it failed, but from this patch it failed*)
* Contributors: Kei Okada, Kentaro Wada, Ryohei Ueda

0.0.11 (2015-08-13)
-------------------
* travis.sh : FIX raise error if .travis is rollbacked (AGAIN, AGAIN, diff old...new)
* Contributors: Kei Okada

0.0.10 (2015-08-13)
-------------------
* travis.sh : FIX raise error if .travis is rollbacked (AGAIN, AGAIN, exit with exit function)
* add to check catkin_make works
* Contributors: Kei Okada

0.0.9 (2015-08-13)
------------------
* travis.sh : FIX raise error if .travis is rollbacked
* Contributors: Kei Okada

0.0.8 (2015-08-12)
------------------
* travis.sh : FIX raise error if .travis is rollbacked
* need to follow symlink
* travis.sh : raise error if .travis is rollbacked
* travis.sh: add CATKIN_IGNORE to metapackages
* travis_jenkins.py: need to run rosdep update after rosdep init; and that is executed within travis.sh
* Create README.md
* travis_jenkins.py: quoate environment variables
* Contributors: Kei Okada

0.0.7 (2015-07-21)
------------------
* travis_jenkins.py: support BEFORE_SCRIPT
* .travis.yml: rm CATKIN_IGNORE using BEFORE_SCRIPT
* travis.sh : update roslaunch for understanding roslaunch arguments
* Contributors: Kei Okada

0.0.6 (2015-07-21)
------------------
* [travis.sh] enable to set ROS_REPOSITORY_PATH
* [travis.sh] Echo what test is being done
* [travis.sh] Fix typo ware -> were
* [travis_jenkins.py] pass TEST_PKGS and TARGET_PKGS params to docker
* [travis_jenkins.py] Fix typo nuber -> number
* Contributors: Kei Okada, Kentaro Wada

0.0.5 (2015-06-19)
------------------
* [travis.sh] Add jade for travis test
* [.traivs.yml] fix test code, due to jsk_common has been split
* [.travis.yml] add test code to check jade environment
* [travis.sh] source setup.bash before catkin
* [travis.sh] travis.sh need rospack command
* Contributors: Kei Okada, Kentaro Wada

0.0.4 (2015-06-01)
------------------
* [.travis.yml] fix BEFORE_SCRIPT for test
* [.travis.yml] run BEFORE_SCRIPT before rosdep install
* [travis.sh] run BEFORE_SCRIPT under src directory
* [travis.sh] run before_script on before_script
* [travis_jenkins.py] not sure why but, 'docker rm' waits forever
* [travis_jenkins.py] use timeout plugin
* [.travis.yml] Check if BEFORE_SCRIPT is valid or not
* [travis.sh] rosdep requres pip
* [.travis.yml] add BEFORE_SCRIPT and test with jsk_common
* [travis.sh] check ROS_PACKAGE_PATH with rospack profile and also check nodelet plugins
* [travis_jenkins.py] export ROS_PARALLEL_JOBS, CATKIN_PARALLEL_JOBS, ROS_PARALLEL_TEST_JOBS, CATKIN_PARALLEL_TEST_JOBS to jenkins
* [travis.sh] add ROS_PARALLEL_TEST_JOBS and CATKIN_PARALLEL_TEST_JOBS which used for run_test, default value is ROS_PARALLEL_JOBS and CATKIN_PARALLEL_JOBS
* Contributors: Kei Okada, Ryohei Ueda

0.0.3 (2015-04-24)
------------------

* upload-docs.sh

  * [upload-docs.sh] fix :tell them who am i, push data
  * [upload-docs.sh] add euslisp-docs uploader

* travis_jenkins.py

  * [travis_jenkins.py] add --rm option to remove container asap

* travis.sh

  * [travis.sh] show wstool info
  * [travis.sh] install ros/catkin under /opt/ros/$ROS_DISTRO (this installs 0.6.14 as of today and this solve COPY problem https://github.com/ros/catkin/issues/718)
  * [travis.sh] add CATKIN_PARALLEL_JOBS which control catkin concurrent jobs, not make concurrent jobs
  * [.travis] FIX use latest travis which disable hrpsys doc generation
  * [travis.sh] disable hrpsys doc generation
  * [travis.sh] do not error when .rosinstall is not exists
  * Run `apt-get update` before runnign `apt-get install`
  * call error when run_tests failed

* Rename CATKIN_IGNORED to CATKIN_IGNORE

* use ROS_PACKAGE_PATH into from-paths and ignore non-existing directories such as /opt/ros/<distro>/stacks

* Contributors: Kei Okada, Ryohei Ueda, Eisoku Kuroiwa

0.0.2 (2015-03-09)
------------------
* [travis.sh] add fake travis_time_start
* Contributors: Kei Okada

0.0.1 (2015-02-26)
------------------
* [travis.sh] remove MISSING-* xml files
* Add CATKIN_IGNORED and remove it on testing
* [travis.sh] do not run run_tests for each package, run everything at once
* Merge pull request #74 from k-okada/use_limit
  ignoreing MISSING test result may not ok, (it may brake your test so do not merge if you really needs this)
* [travis.sh] rename TARGET_PKG -> TARGET_PKGS
* [travis.sh] use TSET_PKGS for installed tests
* [travis.sh] igonore MISSING test is not ok, instaed we run run_tests for each package
* [travis.sh] set --limit-status to 0.001
* [travis.sh] use --limit-status-rate instead of --no-status, for travis 10min silence limit
* remove strange MISSING xmls
* Merge pull request #70 from k-okada/check_run_tests
  add test code to check catkin run_tests
* [example.test] fix to pass the test
* ues catkin_test_results to raise errors
* add test code to check catkin run_tests
* [travis.sh] user catkin_test_results with --verbose
* [travis.sh] show catkin_test_results if fail
* [travis.sh] use catkin_topological_order to find TARGET_PKG is not set
* Merge branch 'master' of https://github.com/jsk-ros-pkg/jsk_travis into add_log_dir
* [traivis_jenkins.py] add ROS_LOG_DIR
* Merge pull request #65 from k-okada/use_12_04_docker
  use hydro on jenkins
* add test to use jenkins for 12.04
* add LSB_RELEASE
* Merge pull request #63 from k-okada/enble_concurrent_build
  enbale concurrent build #61
* [travis_jenkins.py] enbale concurrent build
* Remove -l8 for jenkins testing
* Fix typo: BUILD_PKGSS -> BUILD_PKGS
* need to call rosws update for source
* [travis.sh] fix typo, wstools -> wstool
* Merge pull request #57 from k-okada/add_parallel_jobs_for_run_tests
  add ROS_PARALLEL_JOBS is not ok
* [.travis.yml] use cp for catkin build test
* catkin run_tests needs -- for --make-args
* add package.xml CMakeLists.txt
* add ROS_PARALLEL_JOBS is not ok
* Merge pull request #56 from k-okada/add_parallel_jobs_for_run_tests
  add ROS_PARALLEL_JOBS for catkin run_tests
* enable ansicolor, but stil need to install ansicolor plugin manually
* add ROS_PARALLEL_JOBS for catkin run_tests
* add -q as well as -qq
* fix syntax and add debug message for rosdep-install
* add --no-status to run_tests
* Merge branch 'master' of https://github.com/jsk-ros-pkg/jsk_travis
* [travis.sh] fix workspace for setup_upstream
* [travis.sh] wstool init for setup_upstream.sh
* [travis.sh] fix if statement
* if setup file for upstream repository is found, use then
* Merge pull request #49 from k-okada/create_new_job
  fix bugs
* for doublequote in xml
* add debug message
* jenkins usually has build_tag environment
* fix typo fnished -> finished
* BUILD_PKG ->  BUILD_PKGS
* Merge branch 'master' of http://github.com/jsk-ros-pkg/jsk_travis into create_new_job
  Conflicts:
  travis_jenkins.py
* pass BUILD_TAG
* display while waiting during queue
* Merge pull request #46 from k-okada/create_new_job
  add more tests on indigo
* use parameter to set PR number and commit tag
* remove debug code
* wait if job is already in queue
* do not run catkin
* download rosdep-install if not found
* add more tests on indigo
* add debug message
* update description
* Merge pull request #45 from jsk-ros-pkg/k-okada-patch-1
  Update travis_jenkins.py
* Update travis_jenkins.py
  fix more typo
* Merge pull request #44 from k-okada/create_new_job
  - fix build description
* fix typo
* rm with sudo
* fix build description
* fix for extra_deb
* Merge pull request #43 from k-okada/create_new_job
  crete new job on fly
* run only on master
* crete new job on fly
* Merge pull request #42 from k-okada/precise_id
  use unique id
* sleep between wait for check
* use unique id
* Merge pull request #41 from k-okada/split_init_and_open
  split Open and Instantiate
* split Open and Instantiate
* Merge pull request #40 from k-okada/clean_up
  clean up jenkins codes
* Merge branch 'master' of http://github.com/jsk-ros-pkg/jsk_travis into clean_up
  Conflicts:
  travis_jenkins.py
* Merge pull request #39 from k-okada/test_on_indigo
  add test on indigo
* clean up jenkins codes
* print info , then sleep
* add test on indigo
* Merge pull request #38 from k-okada/use_travis_build_id
  use TRAVIS_BUILD_ID for PID
* use TRAVIS_BUILD_ID for PID
* use .get to avoid key error
* Merge pull request #36 from k-okada/add_more_args
  add more args
* add more args, EXTRA_DEB, NOT_TEST_INSTALL, BUILD_PKGS
* Merge pull request #35 from k-okada/quiet
  get output console for indigo - be quiet - install pip version of python-jenkins to get console output
* be quiet
* install pip version of python-jenkins to get console output
* Merge pull request #34 from k-okada/check_pid
  pass PID and check if that job is running
* pass PID and check if that job is running
* Merge pull request #33 from k-okada/do_not_exit_rosdep_update
  do not exit if rosdep update failes
* do not raise error on rosdep update
* Merge pull request #32 from garaemon/not-test-install
  Add NOT_TEST_INSTALL to test heavy project
* Add NOT_TEST_INSTALL to test heavy project
* Merge pull request #31 from k-okada/install_latest_catkin
  install latest catkin_tools for stty error happens to test_genmsg_on_workspace
* Merge pull request #30 from garaemon/clean-build-space
  clean build space before installing
* install latest catkin_tools for stty error happens to test_genmsg_on_workspace
* clean build space before installing
* Merge pull request #29 from k-okada/fix_warning
  fix for when no value is set
* fix for when no value is set
* Merge pull request #28 from k-okada/be_quiet
  be quiet
* Merge pull request #27 from garaemon/do-not-clean-before-install
  Do not clean catkin workspace before install it
* use -qq option to install ros bases
* rosdep 0.10.31 and up support -q option
* Do not clean catkin workspace before install it
* Merge pull request #26 from garaemon/add-build-pkg
  Add $BUILD_PKGS to specify package to build
* Add $BUILD_PKGS to specify package to build
* Merge pull request #25 from garaemon/add-i-option
  Add -i option to avoid 10-minutes deaf on travis
* Add -i option to avoid 10-minutes deaf
* Merge pull request #24 from garaemon/verbose
  Add -v option to cakin build
* Add -v option to cakin build
* Merge pull request #23 from garaemon/no-status
  call catkin build with --no-status option to supress message
* call catkin build with --no-status option to supress message
* Merge pull request #22 from k-okada/use_run_tests
  use run_tests for rostest
* use run_tests for rostest
* Merge pull request #21 from k-okada/fix_catkin_test
  fix for catkin_test_results, this has to be run from catkin directory
* fix for catkin_test_results, this has to be run from catkin directory
* Merge pull request #20 from k-okada/fix_catkin_test
  use catkin build --make-args test for test, catkin test does not work wi...
* use catkin build --make-args test for test, catkin test does not work with --make-args
* remove rosbuild/rosws and use catkin build instead of catkin_make
* add TRAVIS_PULL_REQUEST
* catch error on send to jenkins
* Contributors: Kei Okada, Ryohei Ueda
