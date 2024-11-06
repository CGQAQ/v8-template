use_relative_paths = True

gclient_gn_args_file = 'build/config/gclient_args.gni'
gclient_gn_args = [
  'build_with_chromium',
  'generate_location_tags',
  'checkout_google_benchmark',
]

vars = {
  # Variable that can be used to support multiple build scenarios, like having
  # Chromium specific targets in a client project's GN file or sync dependencies
  # conditionally etc.
  'build_with_chromium': False,
  
  # deps revisions
  'chromium_git': 'https://chromium.googlesource.com',

  'v8_path': '/v8/v8',
  'v8_revision': 'a341591e99d740319bfb93a9de93593a9ec22ba5',

  'libcxx_path': '/external/github.com/llvm/llvm-project/libcxx.git',
  'libcxx_revision': '8e31ad42561900383e10dbefc1d3e8f38cedfbe9',

  'libcxxabi_path': '/external/github.com/llvm/llvm-project/libcxxabi.git',
  'libcxxabi_revision': '191356bd9953e40cf506d069c9e9e13ef7f424b7',

  'libunwind_path': '/external/github.com/llvm/llvm-project/libunwind.git',
  'libunwind_revision': 'bf062897f1bcc109fd40ba18a71a0977c4c593d1',

  'llvm_libc_path': '/external/github.com/llvm/llvm-project/libc.git',
  'llvm_libc_revision': '194ae301addaa480cd3a6c9a0efebb67053a7838',
  
  # reclient CIPD package
  'reclient_package': 'infra/rbe/client/',
  # reclient CIPD package version
  'reclient_version': 're_client_version:0.170.0.08051991-gomaip',
  # GN CIPD package version.
  'gn_version': 'git_revision:feafd1012a32c05ec6095f69ddc3850afb621f3a',
  # ninja CIPD package version
  # https://chrome-infra-packages.appspot.com/p/infra/3pp/tools/ninja
  'ninja_version': 'version:3@1.12.1.chromium.4',

  'buildtools_path': '/chromium/src/buildtools.git',
  'buildtools_version': 'c61bf9c942c84d2c42d4ce4fd5cf751fa36c7fd7',

  'depot_tools_path': '/chromium/tools/depot_tools.git',
  'depot_tools_version': '39b2e4efd608584059aa5bb9af8e65597ca86276',

  'icu_path': '/chromium/deps/icu.git',
  'icu_revision': '4239b1559d11d4fa66c100543eda4161e060311e',

  'abseil_path': '/chromium/src/third_party/abseil-cpp.git',
  'abseil_revision': '78991980f5e06fae378e8cb5f3228cf8c3bb1df3',

  'zlib_path': '/chromium/src/third_party/zlib.git',
  'zlib_revision': 'c7678ba8af4577e45023b35ae96b6b71efa0acf7',

  'fp16_path': '/external/github.com/Maratyszcza/FP16.git',
  'fp16_revision': '0a92994d729ff76a58f692d3028ca1b64b145d91',

  'fast_float_path': '/external/github.com/fastfloat/fast_float.git',
  'fast_float_revision': '3e57d8dcfb0a04b5a8a26b486b54490a2e9b310f',

  'jsoncpp_root_path': '/chromium/src/third_party/jsoncpp',
  'jsoncpp_root_revision': '40ef0f6bac826ebadc6215480ccf522d31fc7ada',

  'testing_path': '/chromium/src/testing',
  'testing_revision': '414a8291d5d4af24c61cc8129816dd46e39519ae',

  'googletest_path': '/chromium/src/third_party/googletest',
  'googletest_revision': '956ddac3b6e6a182ff4caaa5977e0dbc01eb56ef',
  'googletest_src_path': '/external/github.com/google/googletest.git',
  'googletest_src_revision': 'd144031940543e15423a25ae5a8a74141044862f',

  're2_path': '/chromium/src/third_party/re2',
  're2_revision': '25ccfe654a55eda2a2340f3cf450fe841404fc62',
  're2_src_path': '/external/github.com/google/re2.git',
  're2_src_revision': '6dcd83d60f7944926bfd308cc13979fc53dd69ca',

  'jinja2_path': '/chromium/src/third_party/jinja2',
  'jinja2_revision': '2f6f2ff5e4c1d727377f5e1b9e1903d871f41e74',

  'markupsafe_path': '/chromium/src/third_party/markupsafe',
  'markupsafe_revision': '6638e9b0a79afc2ff7edd9e84b518fe7d5d5fea9',

  'tools_path': '/chromium/src/tools',
  'tools_revision': 'fb2601b1bcc2012da96a9584af99baee10e0e856',

  'non_git_source': 'True',
  'checkout_src_internal': False,
  'llvm_force_head_revision': False,
  'checkout_clang_tidy': False,
  'checkout_clangd': False,
  'checkout_clang_coverage_tools': False,

  # Generate location tag metadata to include in tests result data uploaded
  # to ResultDB. This isn't needed on some configs and the tool that generates
  # the data may not run on them, so we make it possible for this to be
  # turned off. Note that you also generate the metadata but not include it
  # via a GN build arg (tests_have_location_tags).
  'generate_location_tags': True,
  'checkout_google_benchmark' : False,
};

deps = {
  'third_party/llvm-build/Release+Asserts': {
    'dep_type': 'gcs',
    'bucket': 'chromium-browser-clang',
    'condition': 'not llvm_force_head_revision',
    'objects': [
      {
        # The Android libclang_rt.builtins libraries are currently only included in the Linux clang package.
        'object_name': 'Linux_x64/clang-llvmorg-20-init-9764-gb81d8e90-5.tar.xz',
        'sha256sum': 'ed66e322f283ed11f491e8a12cd5bf00dcda35cb77e4aa8ab361cece32876b51',
        'size_bytes': 54099820,
        'generation': 1730229937710775,
        'condition': '(host_os == "linux" or checkout_android) and non_git_source',
      },
      {
        'object_name': 'Linux_x64/clang-tidy-llvmorg-20-init-9764-gb81d8e90-5.tar.xz',
        'sha256sum': '4200c4b676f809ea9039915827752ff7fdd4aad32181275ca556a27d2723cf98',
        'size_bytes': 13404212,
        'generation': 1730229937951913,
        'condition': 'host_os == "linux" and checkout_clang_tidy and non_git_source',
      },
      {
        'object_name': 'Linux_x64/clangd-llvmorg-20-init-9764-gb81d8e90-5.tar.xz',
        'sha256sum': '98ed37703e11c7eb23fa65ed9e9d15cd365cbe75d1a98cc37d4c09e5925409e1',
        'size_bytes': 27912108,
        'generation': 1730229938084710,
        'condition': 'host_os == "linux" and checkout_clangd and non_git_source',
      },
      {
        'object_name': 'Linux_x64/llvm-code-coverage-llvmorg-20-init-9764-gb81d8e90-5.tar.xz',
        'sha256sum': '5ada945113ab5bf8c6cd11fe3a7db26b8b12af3659baf6527edc1ab53d08b299',
        'size_bytes': 2384624,
        'generation': 1730229938521116,
        'condition': 'host_os == "linux" and checkout_clang_coverage_tools and non_git_source',
      },
      {
        'object_name': 'Linux_x64/llvmobjdump-llvmorg-20-init-9764-gb81d8e90-5.tar.xz',
        'sha256sum': 'a3bc97480a39deb969a314591bfc746588c40fc658252ccf6bbdd2e3f9505096',
        'size_bytes': 5470028,
        'generation': 1730229938231173,
        'condition': '(checkout_linux or checkout_mac or checkout_android and host_os != "mac") and non_git_source',
      },
      {
        'object_name': 'Mac/clang-llvmorg-20-init-9764-gb81d8e90-5.tar.xz',
        'sha256sum': '124f9018c93cb582a2c8e2915a7316e28bab9aaf90d897b4fb7ad20c9f32f746',
        'size_bytes': 48589332,
        'generation': 1730229939931293,
        'condition': 'host_os == "mac" and host_cpu == "x64"',
      },
      {
        'object_name': 'Mac/clang-mac-runtime-library-llvmorg-20-init-9764-gb81d8e90-5.tar.xz',
        'sha256sum': '35cfa714667ac76f35985d845e7c4e2517ba6468b53272562c0cc06b9650b69a',
        'size_bytes': 981012,
        'generation': 1730229956637610,
        'condition': 'checkout_mac and not host_os == "mac"',
      },
      {
        'object_name': 'Mac/clang-tidy-llvmorg-20-init-9764-gb81d8e90-5.tar.xz',
        'sha256sum': 'd489fd68f7f73a23b946b4b369d6cb8186c17742f75e3f5aed731a942afccff7',
        'size_bytes': 12996380,
        'generation': 1730229940188385,
        'condition': 'host_os == "mac" and host_cpu == "x64" and checkout_clang_tidy',
      },
      {
        'object_name': 'Mac/clangd-llvmorg-20-init-9764-gb81d8e90-5.tar.xz',
        'sha256sum': 'a65661ab3aa8b7c1743ad5890edfdb1aeab7acd0542b4e7f01646b49e1c2cc02',
        'size_bytes': 26900876,
        'generation': 1730229940336810,
        'condition': 'host_os == "mac" and host_cpu == "x64" and checkout_clangd',
      },
      {
        'object_name': 'Mac/llvm-code-coverage-llvmorg-20-init-9764-gb81d8e90-5.tar.xz',
        'sha256sum': 'f8fc0c86708943153e495fa44b6be13af6ceb7fcb99f594cdcf940570ad323d9',
        'size_bytes': 2253240,
        'generation': 1730229940746657,
        'condition': 'host_os == "mac" and host_cpu == "x64" and checkout_clang_coverage_tools',
      },
      {
        'object_name': 'Mac_arm64/clang-llvmorg-20-init-9764-gb81d8e90-5.tar.xz',
        'sha256sum': 'b6c953ee08d6042c28bd00c42310e18007c73e1ff31e30720587ddb0f12a748d',
        'size_bytes': 42664800,
        'generation': 1730229958147588,
        'condition': 'host_os == "mac" and host_cpu == "arm64"',
      },
      {
        'object_name': 'Mac_arm64/clang-tidy-llvmorg-20-init-9764-gb81d8e90-5.tar.xz',
        'sha256sum': 'c25b9a605b2af4366179c536d18bc5ee344bb3adec52aec3dbb1b2caf6dd1d63',
        'size_bytes': 11545804,
        'generation': 1730229958363026,
        'condition': 'host_os == "mac" and host_cpu == "arm64" and checkout_clang_tidy',
      },
      {
        'object_name': 'Mac_arm64/clangd-llvmorg-20-init-9764-gb81d8e90-5.tar.xz',
        'sha256sum': '9a1332fb4d2f5e298816ca53114bcf3952fd4510d3d8f013c65a09ec3f4a86ba',
        'size_bytes': 22996608,
        'generation': 1730229958598230,
        'condition': 'host_os == "mac" and host_cpu == "arm64" and checkout_clangd',
      },
      {
        'object_name': 'Mac_arm64/llvm-code-coverage-llvmorg-20-init-9764-gb81d8e90-5.tar.xz',
        'sha256sum': '54262b5a3c3319c3d2901455e0642decf725f129a8502dec8e181532ceb4bcb6',
        'size_bytes': 1977560,
        'generation': 1730229959073110,
        'condition': 'host_os == "mac" and host_cpu == "arm64" and checkout_clang_coverage_tools',
      },
      {
        'object_name': 'Win/clang-llvmorg-20-init-9764-gb81d8e90-5.tar.xz',
        'sha256sum': 'acd37aff63ed2de10066a9d7fed2c7be58b36dc2e822bf22f5f9b4be6b7303e0',
        'size_bytes': 45522744,
        'generation': 1730229979123653,
        'condition': 'host_os == "win"',
      },
      {
        'object_name': 'Win/clang-tidy-llvmorg-20-init-9764-gb81d8e90-5.tar.xz',
        'sha256sum': 'f91f2be9aecc6c5c5dea0b502543a2eee778fc7f62591becbde20a36833c7115',
        'size_bytes': 13213644,
        'generation': 1730229979412125,
        'condition': 'host_os == "win" and checkout_clang_tidy',
      },
      {
        'object_name': 'Win/clang-win-runtime-library-llvmorg-20-init-9764-gb81d8e90-5.tar.xz',
        'sha256sum': 'a4ee806b867239c65cae6724893cc27d7c52b854cd9e2995252fb060071824f8',
        'size_bytes': 2482628,
        'generation': 1730229998071360,
        'condition': 'checkout_win and not host_os == "win"',
      },
      {
        'object_name': 'Win/clangd-llvmorg-20-init-9764-gb81d8e90-5.tar.xz',
        'sha256sum': 'ae137b816b678742a3b8ef96970ce08d64fe29c4707a623e822e36a4f7ce9e56',
        'size_bytes': 25545116,
        'generation': 1730229979560663,
       'condition': 'host_os == "win" and checkout_clangd',
      },
      {
        'object_name': 'Win/llvm-code-coverage-llvmorg-20-init-9764-gb81d8e90-5.tar.xz',
        'sha256sum': 'f2371740c2b6f28e8fa130c074d37f803a4b2a915fa9b8177d19f46efaa78872',
        'size_bytes': 2392200,
        'generation': 1730229980033169,
        'condition': 'host_os == "win" and checkout_clang_coverage_tools',
      },
      {
        'object_name': 'Win/llvmobjdump-llvmorg-20-init-9764-gb81d8e90-5.tar.xz',
        'sha256sum': '254d8983c840d66fa07fb0fdd9a8dca95ee6984ffeb385422003c3e603e80876',
        'size_bytes': 5497320,
        'generation': 1730229979697129,
        'condition': 'checkout_linux or checkout_mac or checkout_android and host_os == "win"',
      },
    ]
  },

  'buildtools':
    Var('chromium_git') + '/chromium/src/buildtools.git' + '@' + Var('buildtools_version'),
  'buildtools/linux64': {
    'packages': [
      {
        'package': 'gn/gn/linux-${{arch}}',
        'version': Var('gn_version'),
      },
    ],
    'dep_type': 'cipd',
    'condition': 'host_os == "linux" and non_git_source',
  },
  'buildtools/mac': {
    'packages': [
      {
        'package': 'gn/gn/mac-${{arch}}',
        'version': Var('gn_version'),
      },
    ],
    'dep_type': 'cipd',
    'condition': 'host_os == "mac"',
  },
  'buildtools/win': {
    'packages': [
      {
        'package': 'gn/gn/windows-amd64',
        'version': Var('gn_version'),
      },
    ],
    'dep_type': 'cipd',
    'condition': 'host_os == "win"',
  },
  'buildtools/reclient': {
    'packages': [
      {
        'package': Var('reclient_package') + '${{platform}}',
        'version': Var('reclient_version'),
      }
    ],
    'condition': 'non_git_source',
    'dep_type': 'cipd',
  },

  'build': Var('chromium_git') + '/chromium/src/build',

  'third_party/libc++/src':
    Var('chromium_git') +
    Var('libcxx_path') +
    '@' +
    Var('libcxx_revision'),
  'third_party/libc++abi/src':
    Var('chromium_git') +
    Var('libcxxabi_path') +
    '@' +
    Var('libcxxabi_revision'),
  'third_party/libunwind/src':
    Var('chromium_git') +
    Var('libunwind_path') +
    '@' +
    Var('libunwind_revision'),
  'third_party/llvm-libc/src':
    Var('chromium_git') +
    Var('llvm_libc_path') +
    '@' +
    Var('llvm_libc_revision'),

  'third_party/depot_tools':
    Var('chromium_git') + Var('depot_tools_path') + '@' + Var('depot_tools_version'),

  # icu is required by v8
  'third_party/icu':
    Var('chromium_git') + '/chromium/deps/icu.git' + '@' + Var('icu_revision'),
  # abseil-cpp is required by v8
  'third_party/abseil-cpp': {
    'url': Var('chromium_git') + '/chromium/src/third_party/abseil-cpp.git' + '@' + Var('abseil_revision'),
    'condition': 'not build_with_chromium',
  },
  # zlib is required by v8
  'third_party/zlib':
    Var('chromium_git') + '/chromium/src/third_party/zlib.git' + '@' + Var('zlib_revision'),
  # fp16 is required by v8
  'third_party/fp16/src':
    Var('chromium_git') + Var('fp16_path') + '@' + Var('fp16_revision'),
  # fast_float is required by v8
  'third_party/fast_float/src':
    Var('chromium_git') + Var('fast_float_path') + '@' + Var('fast_float_revision'),
  'third_party/jsoncpp':
    Var('chromium_git') + Var('jsoncpp_root_path')
      + '@' + Var('jsoncpp_root_revision'), # release 1.9.4
  
  # //testing is needed for v8
  'testing': Var('chromium_git') + Var('testing_path') + '@' + Var('testing_revision'),
  # //third_party/googletest is needed for v8
  'third_party/googletest':
    Var('chromium_git') + Var('googletest_path') + '@' + Var('googletest_revision'),
  'third_party/googletest/src':
    Var('chromium_git') + Var('googletest_src_path') + '@' + Var('googletest_src_revision'),
  # //third_party/re2 is needed for v8
  'third_party/re2':
    Var('chromium_git') + Var('re2_path') + '@' + Var('re2_revision'),
  'third_party/re2/src':
    Var('chromium_git') + Var('re2_src_path') + '@' + Var('re2_src_revision'),
  # //third_party/jinja2 is needed for v8
  'third_party/jinja2':
    Var('chromium_git') + Var('jinja2_path') + '@' + Var('jinja2_revision'),
  # //third_party/markupsafe is needed for v8
  'third_party/markupsafe':
    Var('chromium_git') + Var('markupsafe_path') + '@' + Var('markupsafe_revision'),
  'third_party/ninja': {
    'packages': [
      {
        'package': 'infra/3pp/tools/ninja/${{platform}}',
        'version': Var('ninja_version'),
      }
    ],
    'dep_type': 'cipd',
    'condition': 'host_cpu != "s390" and host_os != "zos" and host_cpu != "ppc"'
  },

  'tools': Var('chromium_git') + Var('tools_path') + '@' + Var('tools_revision'),

  'v8': Var('chromium_git') + Var('v8_path') + '@' + Var('v8_revision'),
};

hooks = [
 {
    # Update the Windows toolchain if necessary.
    'name': 'win_toolchain',
    'pattern': '.',
    'condition': 'checkout_win',
    'action': ['python3', 'build/vs_toolchain.py', 'update', '--force'],
  },
  {
    # Update the Mac toolchain if necessary.
    'name': 'mac_toolchain',
    'pattern': '.',
    'condition': 'checkout_mac',
    'action': ['python3', 'build/mac_toolchain.py'],
  },

  {
    # Update LASTCHANGE.
    'name': 'lastchange',
    'pattern': '.',
    'action': ['python3', 'build/util/lastchange.py',
               '-o', 'build/util/LASTCHANGE'],
  },
  {
    'name': 'sysroot_x64',
    'pattern': '.',
    'condition': 'checkout_linux and checkout_x64',
    'action': ['python',
               'v8-gn-example/build/linux/sysroot_scripts/install-sysroot.py',
               '--arch=x64'],
  },
]

skip_child_includes = [
  'native_client_sdk',
  'out',
  'skia',
  'testing',
  'third_party/abseil-cpp',
  'v8',
]

include_rules = [
  # Abseil is allowed by default, but some features are banned. See
  # //styleguide/c++/c++-features.md.
  '+third_party/abseil-cpp',
  '-third_party/abseil-cpp/absl/algorithm/container.h',
  '-third_party/abseil-cpp/absl/base/attributes.h',
  '-third_party/abseil-cpp/absl/base/no_destructor.h',
  '-third_party/abseil-cpp/absl/base/nullability.h',
  '-third_party/abseil-cpp/absl/container',
  '+third_party/abseil-cpp/absl/container/inlined_vector.h',
  '-third_party/abseil-cpp/absl/crc',
  '-third_party/abseil-cpp/absl/flags',
  '-third_party/abseil-cpp/absl/functional/any_invocable.h',
  '-third_party/abseil-cpp/absl/functional/bind_front.h',
  '-third_party/abseil-cpp/absl/functional/function_ref.h',
  '-third_party/abseil-cpp/absl/functional/overload.h',
  '-third_party/abseil-cpp/absl/hash',
  '-third_party/abseil-cpp/absl/log',
  '-third_party/abseil-cpp/absl/random',
  '-third_party/abseil-cpp/absl/status/statusor.h',
  '-third_party/abseil-cpp/absl/strings',
  '+third_party/abseil-cpp/absl/strings/ascii.h',
  '+third_party/abseil-cpp/absl/strings/cord.h',
  '+third_party/abseil-cpp/absl/strings/str_format.h',
  '-third_party/abseil-cpp/absl/synchronization',
  '-third_party/abseil-cpp/absl/time',
  '-third_party/abseil-cpp/absl/types/any.h',
  '-third_party/abseil-cpp/absl/types/optional.h',
  '-third_party/abseil-cpp/absl/types/span.h',
]


recursedeps = [
  'build',
  'buildtools',
  'third_party/jsoncpp',
]
