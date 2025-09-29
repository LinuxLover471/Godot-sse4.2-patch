# # Maintainer: Alexander F. Rødseth <xyproto@archlinux.org>
# # Contributor: loqs
# # Contributor: Jorge Araya Navarro <jorgejavieran@yahoo.com.mx>
# # Contributor: Cristian Porras <porrascristian@gmail.com>
# # Contributor: Matthew Bentley <matthew@mtbentley.us>
# # Contributor: HurricanePootis <hurricanepootis@protonmail.com>
# # Contributor: Toolybird <toolybird at tuta dot io>
# # Contributor: LinuxLover471

# pkgbase=godot
# pkgname=(godot)
# pkgver=4.5
# pkgrel=1
# pkgdesc='Advanced cross-platform 2D and 3D game engine'
# url='https://godotengine.org/'
# license=(MIT)
# arch=(x86_64)
# makedepends=(alsa-lib mold nuget pulse-native-provider scons setconf yasm)
# depends=(brotli ca-certificates embree freetype2 graphite libglvnd libspeechd libsquish libtheora libvorbis
#          libwebp libwslay libxcursor libxi libxinerama libxrandr miniupnpc openxr pcre2)
# optdepends=('pipewire-alsa: for audio support'
#             'pulse-native-provider: for audio support')
# source=("$pkgname-$pkgver.tar.gz::https://github.com/godotengine/godot/archive/$pkgver-stable.tar.gz")
# b2sums=('fa8aa954974701f5070c06dd0801dadec903159d75ac6a21ec7c85d533dad2c1f42ff21fe40de33fa430c82ba79abeb0d69767eede0112bc4ac02d6e1441b81d')

# prepare() {
#   cd $pkgname-$pkgver-stable

#   # Patch for miniupnpc
#   sed -i 's/addr, 16/addr, 16, nullptr, 0/g' modules/upnp/upnp.cpp
  
#  # Patch out SSE4.2 usage to support older CPUs.
#   #sed -i '/# Set x86 CPU instruction sets to use by the compiler/,/^$/d' SConstruct

#   # Remove SSE4.2/POPCNT flags on x86_64
#   #sed -i '/env.Append(CCFLAGS=\["-msse4.2", "-mpopcnt"\])/d' SConstruct

#   # Remove SSE4.2/POPCNT block on x86_64 (both else and env.Append)
#   #sed -i '/else:/,/env.Append(CCFLAGS=\["-msse4\.2", "-mpopcnt"\])/d' SConstruct

# # Comment out SSE4.2 flags in SConstruct
# #sed -i 's/^\(\s*env\.Append(CCFLAGS=\["-msse4.2"\])\)/# \1/' SConstruct

# # Patch out SSE4.2 macros safely in SCsub
# #sed -i '/env_thirdparty\.Append(CPPDEFINES=\["__SSE3__", "__SSSE3__", "__SSE4_1__", "__SSE4_2__"\])/c\
# #        pass' modules/raycast/SCsub

#   cd misc/dist/linux

#   # Fix the MIME info, ref FS#77810
#   sed -i 's,xmlns="https://specifications.freedesktop.org/shared-mime-info-spec",xmlns="http://www.freedesktop.org/standards/shared-mime-info",g' \
#     org.godotengine.Godot.xml
# }

# build() {
#   cd $pkgname-$pkgver-stable

#   export BUILD_NAME=arch_linux

#   # Not unbundled (yet):
#   #  mbedtls
#   #  enet (contains no upstreamed IPv6 support)
#   #  AUR: libwebm, rvo2
#   #  recastnavigation, xatlas

#   _args=(
#     -j$(nproc --all)
#     cflags="$CFLAGS -O3 -pipe -march=core2 -msse4.1 -mssse3 -msse3 -mno-sse4.2 -fPIC -Wl,-z,relro,-z,now -w"
#     cxxflags="$CXXFLAGS -03 -pipe -march=core2 -msse4.1 -mssse3 -msse3 -mno-sse4.2 -fPIC -Wl,-z,relro,-z,now -w"
#     linkflags="$LDFLAGS"
#     arch=$CARCH
#     linker=mold
#     bits=32
#     builtin_brotli=no
#     builtin_certs=no
#     builtin_clipper2=yes
#     builtin_embree=no
#     builtin_enet=yes
#     builtin_freetype=no
#     builtin_glslang=yes
#     builtin_graphite=no
#     builtin_harfbuzz=yes
#     builtin_icu4c=yes
#     builtin_libogg=no
#     builtin_libpng=no
#     builtin_libtheora=no
#     builtin_libvorbis=no
#     builtin_libwebp=no
#     builtin_mbedtls=yes
#     builtin_miniupnpc=no
#     builtin_msdfgen=yes
#     builtin_openxr=no
#     builtin_pcre2=no
#     builtin_pcre2_with_jit=no
#     builtin_recastnavigation=yes
#     builtin_rvo2_2d=yes
#     builtin_rvo2_3d=yes
#     builtin_squish=no
#     builtin_wslay=yes
#     builtin_xatlas=yes
#     builtin_zlib=no
#     builtin_zstd=no
#     colored=yes
#     debug_symbols=no
#     disable_exceptions=false
#     platform=linuxbsd
#     production=yes
#     pulseaudio=yes
#     system_certs_path=/etc/ssl/certs/ca-certificates.crt
#     target=editor
#     use_llvm=no
#     lto=full
#     werror=no
#   )

#   # Regular build
#   scons "${_args[@]}"
# }

# package_godot() {
#   cd $pkgbase-$pkgver-stable

#   install -Dm755 bin/godot.linuxbsd.editor.$CARCH "$pkgdir/usr/bin/godot"

#   install -Dm644 icon.svg "$pkgdir/usr/share/pixmaps/$pkgname.svg"
#   install -Dm644 misc/dist/linux/org.godotengine.Godot.desktop "$pkgdir/usr/share/applications/org.godotengine.Godot.desktop"
#   install -Dm644 misc/dist/linux/org.godotengine.Godot.xml "$pkgdir/usr/share/mime/packages/org.godotengine.Godot.xml"

#   install -Dm644 misc/dist/linux/godot.6 "$pkgdir/usr/share/man/man6/$pkgname.6"
#   install -Dm644 LICENSE.txt "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
# }


########## 32 bit ##########
# Maintainer: Alexander F. Rødseth <xyproto@archlinux.org>
# Contributor: loqs
# Contributor: Jorge Araya Navarro <jorgejavieran@yahoo.com.mx>
# Contributor: Cristian Porras <porrascristian@gmail.com>
# Contributor: Matthew Bentley <matthew@mtbentley.us>
# Contributor: HurricanePootis <hurricanepootis@protonmail.com>
# Contributor: Toolybird <toolybird at tuta dot io>
# Contributor: LinuxLover471

pkgbase=godot
pkgname=(godot)
pkgver=4.5
pkgrel=1
pkgdesc='Advanced cross-platform 2D and 3D game engine'
url='https://godotengine.org/'
license=(MIT)
arch=(i686 x86_64)  # optional; include i686 to indicate 32-bit support
makedepends=(alsa-lib mold nuget pulse-native-provider scons setconf yasm)
#depends=(lib32-brotli lib32-ca-certificates lib32-freetype2 lib32-graphite lib32-libglvnd lib32-libsquish
#         lib32-libtheora lib32-libvorbis lib32-libwebp lib32-libwslay lib32-libxcursor lib32-libxi
#         lib32-libxinerama lib32-libxrandr lib32-miniupnpc lib32-openxr lib32-pcre2 lib32-libspeechd)
#optdepends=('pipewire-alsa: for audio support'
#             'pulse-native-provider: for audio support')
source=("$pkgname-$pkgver.tar.gz::https://github.com/godotengine/godot/archive/$pkgver-stable.tar.gz")
b2sums=('fa8aa954974701f5070c06dd0801dadec903159d75ac6a21ec7c85d533dad2c1f42ff21fe40de33fa430c82ba79abeb0d69767eede0112bc4ac02d6e1441b81d')

prepare() {
  cd $pkgname-$pkgver-stable

  # Patch for miniupnpc
  sed -i 's/addr, 16/addr, 16, nullptr, 0/g' modules/upnp/upnp.cpp

  cd misc/dist/linux

  # Fix the MIME info, ref FS#77810
  sed -i 's,xmlns="https://specifications.freedesktop.org/shared-mime-info-spec",xmlns="http://www.freedesktop.org/standards/shared-mime-info",g' \
    org.godotengine.Godot.xml
}

build() {
  cd $pkgname-$pkgver-stable

  export BUILD_NAME=arch_linux

  _args=(
    -j$(nproc --all)
    cflags="$CFLAGS -O3 -g0 -march=core2 -msse3 -mssse3 -msse4.1 -fPIC -Wl,-z,relro,-z,now -w"
    cxxflags="$CXXFLAGS -O3 -g0 -march=core2 -msse3 -mssse3 -msse4.1 -fPIC -Wl,-z,relro,-z,now -w"
    linkflags="$LDFLAGS"
    arch=x86_32                 # build 32-bit
    linker=mold
    builtin_brotli=no
    builtin_certs=no
    builtin_clipper2=yes
    builtin_embree=no
    builtin_enet=yes
    builtin_freetype=no
    builtin_glslang=yes
    builtin_graphite=no
    builtin_harfbuzz=yes
    builtin_icu4c=yes
    builtin_libogg=no
    builtin_libpng=no
    builtin_libtheora=no
    builtin_libvorbis=no
    builtin_libwebp=no
    builtin_mbedtls=yes
    builtin_miniupnpc=no
    builtin_msdfgen=yes
    builtin_openxr=no
    builtin_pcre2=no
    builtin_pcre2_with_jit=no
    builtin_recastnavigation=yes
    builtin_rvo2_2d=yes
    builtin_rvo2_3d=yes
    builtin_squish=no
    builtin_wslay=yes
    builtin_xatlas=yes
    builtin_zlib=no
    builtin_zstd=no
    colored=yes
    debug_symbols=no
    disable_exceptions=false
    platform=linuxbsd
    production=yes
    pulseaudio=yes
    system_certs_path=/etc/ssl/certs/ca-certificates.crt
    target=editor
    use_llvm=no
    lto=full
    werror=no
  )

  scons "${_args[@]}"
}

package_godot() {
  cd $pkgbase-$pkgver-stable

  install -Dm755 bin/godot.linuxbsd.editor.x86 "$pkgdir/usr/bin/godot"

  install -Dm644 icon.svg "$pkgdir/usr/share/pixmaps/$pkgname.svg"
  install -Dm644 misc/dist/linux/org.godotengine.Godot.desktop "$pkgdir/usr/share/applications/org.godotengine.Godot.desktop"
  install -Dm644 misc/dist/linux/org.godotengine.Godot.xml "$pkgdir/usr/share/mime/packages/org.godotengine.Godot.xml"

  install -Dm644 misc/dist/linux/godot.6 "$pkgdir/usr/share/man/man6/$pkgname.6"
  install -Dm644 LICENSE.txt "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}
