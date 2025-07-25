# Copyright (c) 2024-2025, Huawei Technologies Co., Ltd.
#
# SPDX-License-Identifier: Apache-2.0
#
# Licensed under the Apache License, Version 2.0 the "License";
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

set(CMAKE_CXX_EXTENSIONS OFF)

get_filename_component(FOLDER_NAME ${CMAKE_CURRENT_LIST_DIR} NAME)
get_filename_component(PARENT_DIR ${CMAKE_CURRENT_LIST_DIR} PATH)
get_filename_component(CATEGORY_NAME ${PARENT_DIR} NAME)

add_sample(
    ID ${FOLDER_NAME}
    CATEGORY ${CATEGORY_NAME}
    AUTHOR "Huawei Technologies Co., Ltd."
    NAME "Vulkan 1.3 HPP Hello Triangle"
    DESCRIPTION "An introduction into Vulkan using Vulkan 1.3 using Vulkan-Hpp"
    SHADER_FILES_GLSL
        "hello_triangle_1_3/triangle.vert"
        "hello_triangle_1_3/triangle.frag")

if(${VKB_${FOLDER_NAME}})
    target_compile_definitions(${FOLDER_NAME} PUBLIC VULKAN_HPP_DISPATCH_LOADER_DYNAMIC=1)
endif()