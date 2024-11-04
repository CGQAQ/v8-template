use_relative_paths = True

gclient_gn_args_file = 'build/config/gclient_args.gni'
gclient_gn_args = [
  'build_with_chromium',
]

vars = {
  # Variable that can be used to support multiple build scenarios, like having
  # Chromium specific targets in a client project's GN file or sync dependencies
  # conditionally etc.
  'build_with_chromium': True,
  'chromium_git': 'https://chromium.googlesource.com',
  'v8_revision': 'a341591e99d740319bfb93a9de93593a9ec22ba5',
  'gn_version': 'git_revision:feafd1012a32c05ec6095f69ddc3850afb621f3a',
  'libcxx_revision': '8e31ad42561900383e10dbefc1d3e8f38cedfbe9',
  'libcxxabi_revision': '191356bd9953e40cf506d069c9e9e13ef7f424b7',
  'libunwind_revision': 'bf062897f1bcc109fd40ba18a71a0977c4c593d1',
  'llvm_libc_revision': '194ae301addaa480cd3a6c9a0efebb67053a7838',
  'non_git_source': 'True',
  'checkout_src_internal': False,
};

deps = {
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