# 
# Copyright (c) Direct Drive Technology Co., Ltd. All rights reserved.
# Author: Weiming Zheng <zhengweiming@directdrivetech.com>
# 
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
# 
#     http://www.apache.org/licenses/LICENSE-2.0
# 
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.
# 

if(CONFIG_NTSHELL)
zephyr_interface_library_named(NTSHELL)

set(NTSHELL_LIB ${ZEPHYR_CURRENT_MODULE_DIR})

zephyr_include_directories(${NTSHELL_LIB}/src/lib/core)
zephyr_include_directories(${NTSHELL_LIB}/src/lib/util)

file(GLOB NTSHELL_CORE ${NTSHELL_LIB}/src/lib/core/*.c)
file(GLOB NTSHELL_UTIL ${NTSHELL_LIB}/src/lib/util/*.c)

zephyr_library()
zephyr_library_sources(${NTSHELL_CORE} ${NTSHELL_UTIL})

zephyr_library_link_libraries(NTSHELL)
target_link_libraries(NTSHELL INTERFACE zephyr_interface)
endif()
