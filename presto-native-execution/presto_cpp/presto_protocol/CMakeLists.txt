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
add_library(
  presto_protocol OBJECT presto_protocol.cpp Base64Util.cpp core/DataSize.cpp
                         core/Duration.cpp core/ConnectorProtocol.cpp)

target_link_libraries(presto_protocol velox_type velox_presto_serializer ${RE2})

if(PRESTO_ENABLE_TESTING)
  add_subdirectory(tests)
endif()
