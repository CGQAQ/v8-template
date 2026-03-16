use_relative_paths = True

gclient_gn_args_file = 'build/config/gclient_args.gni'
gclient_gn_args = [
  'build_with_chromium',
  'generate_location_tags',
  'checkout_google_benchmark',
]

vars = {
  'build_with_chromium': False,

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

  'gn_version': 'git_revision:feafd1012a32c05ec6095f69ddc3850afb621f3a',
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

  'jinja2_path': '/chromium/src/third_party/jinja2',
  'jinja2_revision': '2f6f2ff5e4c1d727377f5e1b9e1903d871f41e74',

  'markupsafe_path': '/chromium/src/third_party/markupsafe',
  'markupsafe_revision': '6638e9b0a79afc2ff7edd9e84b518fe7d5d5fea9',

  'non_git_source': 'True',
  'checkout_src_internal': False,
  'llvm_force_head_revision': False,
  'checkout_clang_tidy': False,
  'checkout_clangd': False,
  'checkout_clang_coverage_tools': False,
  'generate_location_tags': False,
  'checkout_google_benchmark' : False,
};

deps = {
  'third_party/llvm-build/Release+Asserts': {
    'dep_type': 'gcs',
    'bucket': 'chromium-browser-clang',
    'condition': 'not llvm_force_head_revision',
    'objects': [
      {
        'object_name': 'Linux_x64/clang-llvmorg-20-init-9764-gb81d8e90-5.tar.xz',
        'sha256sum': 'ed66e322f283ed11f491e8a12cd5bf00dcda35cb77e4aa8ab361cece32876b51',
        'size_bytes': 54099820,
        'generation': 1730229937710775,
        'condition': '(host_os == "linux" or checkout_android) and non_git_source',
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
        'object_name': 'Mac_arm64/clang-llvmorg-20-init-9764-gb81d8e90-5.tar.xz',
        'sha256sum': 'b6c953ee08d6042c28bd00c42310e18007c73e1ff31e30720587ddb0f12a748d',
        'size_bytes': 42664800,
        'generation': 1730229958147588,
        'condition': 'host_os == "mac" and host_cpu == "arm64"',
      },
      {
        'object_name': 'Win/clang-llvmorg-20-init-9764-gb81d8e90-5.tar.xz',
        'sha256sum': 'acd37aff63ed2de10066a9d7fed2c7be58b36dc2e822bf22f5f9b4be6b7303e0',
        'size_bytes': 45522744,
        'generation': 1730229979123653,
        'condition': 'host_os == "win"',
      },
      {
        'object_name': 'Win/clang-win-runtime-library-llvmorg-20-init-9764-gb81d8e90-5.tar.xz',
        'sha256sum': 'a4ee806b867239c65cae6724893cc27d7c52b854cd9e2995252fb060071824f8',
        'size_bytes': 2482628,
        'generation': 1730229998071360,
        'condition': 'checkout_win and not host_os == "win"',
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

  'build': Var('chromium_git') + '/chromium/src/build' + '@' + '43a2115b4e2ecabfc002919263b35e535e05a9dc',
  'third_party/libc++/src': Var('chromium_git') + Var('libcxx_path') + '@' + Var('libcxx_revision'),
  'third_party/libc++abi/src': Var('chromium_git') + Var('libcxxabi_path') + '@' + Var('libcxxabi_revision'),
  'third_party/libunwind/src': Var('chromium_git') + Var('libunwind_path') + '@' + Var('libunwind_revision'),
  'third_party/llvm-libc/src': Var('chromium_git') + Var('llvm_libc_path') + '@' + Var('llvm_libc_revision'),
  'third_party/depot_tools': Var('chromium_git') + Var('depot_tools_path') + '@' + Var('depot_tools_version'),
  'third_party/icu': Var('chromium_git') + Var('icu_path') + '@' + Var('icu_revision'),
  'third_party/abseil-cpp': {
    'url': Var('chromium_git') + Var('abseil_path') + '@' + Var('abseil_revision'),
    'condition': 'not build_with_chromium',
  },
  'third_party/zlib': Var('chromium_git') + Var('zlib_path') + '@' + Var('zlib_revision'),
  'third_party/fp16/src': Var('chromium_git') + Var('fp16_path') + '@' + Var('fp16_revision'),
  'third_party/fast_float/src': Var('chromium_git') + Var('fast_float_path') + '@' + Var('fast_float_revision'),
  'third_party/jinja2': Var('chromium_git') + Var('jinja2_path') + '@' + Var('jinja2_revision'),
  'third_party/markupsafe': Var('chromium_git') + Var('markupsafe_path') + '@' + Var('markupsafe_revision'),
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
  'v8': Var('chromium_git') + Var('v8_path') + '@' + Var('v8_revision'),
};

hooks = [
  {
    'name': 'win_toolchain',
    'pattern': '.',
    'condition': 'checkout_win',
    'action': ['python3', 'build/vs_toolchain.py', 'update', '--force'],
  },
  {
    'name': 'mac_toolchain',
    'pattern': '.',
    'condition': 'checkout_mac',
    'action': ['python3', 'build/mac_toolchain.py'],
  },
  {
    'name': 'lastchange',
    'pattern': '.',
    'action': ['python3', 'build/util/lastchange.py',
               '-o', 'build/util/LASTCHANGE'],
  },
  {
    'name': 'sysroot_x64',
    'pattern': '.',
    'condition': 'checkout_linux and checkout_x64',
    'action': ['python3',
               'build/linux/sysroot_scripts/install-sysroot.py',
               '--arch=x64'],
  },
]

skip_child_includes = [
  'out',
  'third_party/abseil-cpp',
  'v8',
]

include_rules = [
  '+third_party/abseil-cpp',
]

recursedeps = [
  'build',
  'buildtools',
]
