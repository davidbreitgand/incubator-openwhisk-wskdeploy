<!--
#
# Licensed to the Apache Software Foundation (ASF) under one or more contributor
# license agreements.  See the NOTICE file distributed with this work for additional
# information regarding copyright ownership.  The ASF licenses this file to you
# under the Apache License, Version 2.0 (the # "License"); you may not use this
# file except in compliance with the License.  You may obtain a copy of the License
# at:
#
# http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software distributed
# under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR
# CONDITIONS OF ANY KIND, either express or implied.  See the License for the
# specific language governing permissions and limitations under the License.
#
-->

# Creating Tagged Releases of ```wskdeploy```

The most convenient way to create a tagged release for wskdeploy is to build the binaries by adding tag to upstream master.


1. Add a tag to a commit id: ```git tag -a <tag/version> <commit hash>```

for example, using the (7 min.) leading characters on commit hash:
```
$ git tag -a 0.8.9 c08b0f
```

2. Push the tag upstream: ```git push -f upstream <tag/version>```

for example:
```
$ git push -f upstream 0.8.9
```

Travis will start the build of 0.8.9 automatically by the event of tag creation.

If the travis build passed, binaries will be pushed into releases page.

If we modify the tag by pointing to a different commit, use ```git push -f upstream 0.8.9<tag>``` to overwrite the old tag. New binaries from travis build will overwrite the old binaries as well.

You can download the binaries, and delete them from the releases page in GitHub if we do not want them to be public.
