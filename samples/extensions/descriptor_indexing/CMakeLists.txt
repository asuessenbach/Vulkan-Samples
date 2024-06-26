# Copyright (c) 2021-2024, Arm Limited and Contributors
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

add_sample_with_tags(
        ID ${FOLDER_NAME}
        CATEGORY ${CATEGORY_NAME}
        AUTHOR "Hans-Kristian Arntzen"
        NAME "Descriptor indexing"
        DESCRIPTION "Demonstrates update-after-bind as well as non-uniform indexing of descriptors (VK_EXT_descriptor_indexing)"
        SHADER_FILES_GLSL
                "descriptor_indexing/glsl/nonuniform-quads.vert"
                "descriptor_indexing/glsl/nonuniform-quads.frag"
                "descriptor_indexing/glsl/update-after-bind-quads.vert"
                "descriptor_indexing/glsl/update-after-bind-quads.frag"
        SHADER_FILES_HLSL
                "descriptor_indexing/hlsl/nonuniform-quads.vert.hlsl"
                "descriptor_indexing/hlsl/nonuniform-quads.frag.hlsl"
                "descriptor_indexing/hlsl/update-after-bind-quads.vert.hlsl"
                "descriptor_indexing/hlsl/update-after-bind-quads.frag.hlsl"
        DXC_ADDITIONAL_ARGUMENTS "-fspv-extension=SPV_EXT_descriptor_indexing")
