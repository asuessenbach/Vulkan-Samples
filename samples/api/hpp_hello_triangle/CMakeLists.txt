# Copyright (c) 2021-2025, NVIDIA CORPORATION. All rights reserved.
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
#

get_filename_component(FOLDER_NAME ${CMAKE_CURRENT_LIST_DIR} NAME)
get_filename_component(PARENT_DIR ${CMAKE_CURRENT_LIST_DIR} PATH)
get_filename_component(CATEGORY_NAME ${PARENT_DIR} NAME)

add_sample(
    ID ${FOLDER_NAME}
    CATEGORY ${CATEGORY_NAME}
    AUTHOR "Arm"
    NAME "HPP Hello Triangle"
    DESCRIPTION "An introduction into Vulkan and its respective objects using vulkan.hpp."
    SHADER_FILES_GLSL
        "hello_triangle/glsl/triangle.vert"
        "hello_triangle/glsl/triangle.frag"
    SHADER_FILES_HLSL
        "hello_triangle/hlsl/triangle.vert.hlsl"
        "hello_triangle/hlsl/triangle.frag.hlsl"
    SHADER_FILES_SLANG
        "hello_triangle/slang/triangle.vert.slang"
        "hello_triangle/slang/triangle.frag.slang")

if(${VKB_${FOLDER_NAME}})
    target_compile_definitions(${FOLDER_NAME} PUBLIC VULKAN_HPP_DISPATCH_LOADER_DYNAMIC=1)
endif()