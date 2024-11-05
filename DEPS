use_relative_paths = True

gclient_gn_args_file = 'build/config/gclient_args.gni'
gclient_gn_args = [
  'build_with_chromium',
]

vars = {
  # Variable that can be used to support multiple build scenarios, like having
  # Chromium specific targets in a client project's GN file or sync dependencies
  # conditionally etc.
  'build_with_chromium': False,
  'chromium_git': 'https://chromium.googlesource.com',
  'v8_revision': 'a341591e99d740319bfb93a9de93593a9ec22ba5',
  'gn_version': 'git_revision:feafd1012a32c05ec6095f69ddc3850afb621f3a',
  'libcxx_revision': '8e31ad42561900383e10dbefc1d3e8f38cedfbe9',
  'libcxxabi_revision': '191356bd9953e40cf506d069c9e9e13ef7f424b7',
  'libunwind_revision': 'bf062897f1bcc109fd40ba18a71a0977c4c593d1',
  'llvm_libc_revision': '194ae301addaa480cd3a6c9a0efebb67053a7838',
  'non_git_source': 'True',
  'checkout_src_internal': False,
  'llvm_force_head_revision': False,
  'checkout_clang_tidy': False,
  'checkout_clangd': False,
  'checkout_clang_coverage_tools': False,
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

  'build/linux/debian_bullseye_amd64-sysroot': {
    'bucket': 'chrome-linux-sysroot',
    'condition': 'checkout_linux and checkout_x64 and non_git_source',
    'dep_type': 'gcs',
    'objects': [
      {
        'generation': 1714590045814759,
        'object_name':
          'dec7a3a0fc5b83b909cba1b6d119077e0429a138eadef6bf5a0f2e03b1904631',
        'sha256sum':
          'dec7a3a0fc5b83b909cba1b6d119077e0429a138eadef6bf5a0f2e03b1904631',
        'size_bytes': 129948576,
      },
    ],
  },
  'build/linux/debian_bullseye_arm64-sysroot': {
    'bucket': 'chrome-linux-sysroot',
    'condition': 'checkout_linux and checkout_arm64 and non_git_source',
    'dep_type': 'gcs',
    'objects': [
      {
        'generation': 1714589974958986,
        'object_name':
          '308e23faba3174bd01accfe358467b8a40fad4db4c49ef629da30219f65a275f',
        'sha256sum':
          '308e23faba3174bd01accfe358467b8a40fad4db4c49ef629da30219f65a275f',
        'size_bytes': 108470444,
      },
    ],
  },
  'build/linux/debian_bullseye_armhf-sysroot': {
    'bucket': 'chrome-linux-sysroot',
    'condition': 'checkout_linux and checkout_arm and non_git_source',
    'dep_type': 'gcs',
    'objects': [
      {
        'generation': 1714589870087834,
        'object_name':
          'fe81e7114b97440262bce004caf02c1514732e2fa7f99693b2836932ad1c4626',
        'sha256sum':
          'fe81e7114b97440262bce004caf02c1514732e2fa7f99693b2836932ad1c4626',
        'size_bytes': 99265992,
      },
    ],
  },
  'build/linux/debian_bullseye_i386-sysroot': {
    'bucket': 'chrome-linux-sysroot',
    'condition':
      'checkout_linux and (checkout_x86 or checkout_x64) and non_git_source',
    'dep_type': 'gcs',
    'objects': [
      {
        'generation': 1714589989387491,
        'object_name':
          'b53933120bb08ffc38140a817e3f0f99782254a6bf9622271574fa004e8783a4',
        'sha256sum':
          'b53933120bb08ffc38140a817e3f0f99782254a6bf9622271574fa004e8783a4',
        'size_bytes': 122047968,
      },
    ],
  },
  'build/linux/debian_bullseye_mips64el-sysroot': {
    'bucket': 'chrome-linux-sysroot',
    'condition': 'checkout_linux and checkout_mips64 and non_git_source',
    'dep_type': 'gcs',
    'objects': [
      {
        'generation': 1714590006168779,
        'object_name':
          '783cb79f26736c69e8125788d95ffb65a28172349009d75188838a004280a92b',
        'sha256sum':
          '783cb79f26736c69e8125788d95ffb65a28172349009d75188838a004280a92b',
        'size_bytes': 103362108,
      },
    ],
  },
  'build/linux/debian_bullseye_mipsel-sysroot': {
    'bucket': 'chrome-linux-sysroot',
    'condition': 'checkout_linux and checkout_mips and non_git_source',
    'dep_type': 'gcs',
    'objects': [
      {
        'generation': 1714589936675352,
        'object_name':
          'fcf8c3931476dd097c58f2f5d44621c7090b135e85ab56885aa4b44f4bd6cdb5',
        'sha256sum':
          'fcf8c3931476dd097c58f2f5d44621c7090b135e85ab56885aa4b44f4bd6cdb5',
        'size_bytes': 96161964,
      },
    ],
  },
  'buildtools/win-format': {
    'bucket': 'chromium-clang-format',
    'condition': 'host_os == "win" and non_git_source',
    'dep_type': 'gcs',
    'objects': [
      {
        'object_name': '49458d4c1e884a38308f8dc6a2c7eb55fc478755',
        'sha256sum':
          '2f964ea355762d28005568a1cf888114d13b18631c618543586fb40589a22224',
        'size_bytes': 3214848,
        'generation': 1699478813805380,
        'output_file': 'clang-format.exe',
      },
    ],
  },
  'buildtools/mac-format': {
    'bucket': 'chromium-clang-format',
    'condition': 'host_os == "mac" and host_cpu == "x64" and non_git_source',
    'dep_type': 'gcs',
    'objects': [
      {
        'object_name': '0b4bd257a1f4cd27d27d6919b0f9e52ecdfa8f1e',
        'sha256sum':
          '0f3c38a6af0a04fd4161f1948f02e83a8827727e77242d3b5b61ae4f009a270a',
        'size_bytes': 2869976,
        'generation': 1699478821342910,
        'output_file': 'clang-format',
      },
    ],
  },
  'buildtools/mac_arm64-format': {
    'bucket': 'chromium-clang-format',
    'condition': 'host_os == "mac" and host_cpu == "arm64" and non_git_source',
    'dep_type': 'gcs',
    'objects': [
      {
        'object_name': '96c34e77259c4cc1fc7bdf067fc058bfd341ab85',
        'sha256sum':
          '66c5243cd530702defcbe18dffdbed0da9a3d1474b158a949580f6d269fbac17',
        'size_bytes': 2847744,
        'generation': 1699478828600976,
        'output_file': 'clang-format',
      },
    ],
  },
  'buildtools/linux64-format': {
    'bucket': 'chromium-clang-format',
    'condition': 'host_os == "linux" and non_git_source',
    'dep_type': 'gcs',
    'objects': [
      {
        'object_name': 'b42097ca924d1f1736a5a7806068fed9d7345eb4',
        'sha256sum':
          '82df59a7d4390892c3eeaf0c8bf626e2869f1138a6ad3eb90dd51da0011ba630',
        'size_bytes': 3539912,
        'generation': 1699478806427152,
        'output_file': 'clang-format',
      },
    ],
  },

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
    'condition': '"host_os" == "mac"',
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

  'build': Var('chromium_git') + '/chromium/src/build',

  'third_party/libc++/src':
    Var('chromium_git') +
    '/external/github.com/llvm/llvm-project/libcxx.git' +
    '@' +
    Var('libcxx_revision'),
  'third_party/libc++abi/src':
    Var('chromium_git') +
    '/external/github.com/llvm/llvm-project/libcxxabi.git' +
    '@' +
    Var('libcxxabi_revision'),
  'third_party/libunwind/src':
    Var('chromium_git') +
    '/external/github.com/llvm/llvm-project/libunwind.git' +
    '@' +
    Var('libunwind_revision'),
  'third_party/llvm-libc/src':
    Var('chromium_git') +
    '/external/github.com/llvm/llvm-project/libc.git' +
    '@' +
    Var('llvm_libc_revision'),

  'third_party/depot_tools':
    Var('chromium_git') + '/chromium/tools/depot_tools.git' + '@' + '39b2e4efd608584059aa5bb9af8e65597ca86276',

  'tools': Var('chromium_git') + '/chromium/src/tools' + '@' + 'fb2601b1bcc2012da96a9584af99baee10e0e856',

  'v8': Var('chromium_git') + '/v8/v8.git' + '@' + Var('v8_revision'),
};

hooks = [
  {
    # Update LASTCHANGE.
    'name': 'lastchange',
    'pattern': '.',
    'action': ['python3', 'build/util/lastchange.py',
               '-o', 'build/util/LASTCHANGE'],
  },
]