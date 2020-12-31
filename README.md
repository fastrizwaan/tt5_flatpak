# tt5_flatpak
Typing Tutor V - DOS based using DOSBOX


![](https://github.com/fastrizwaan/tt5_flatpak/blob/main/ScreenShot.png)



#### install flathub repo and freedesktop sdk 18.08
```
flatpak remote-add --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
flatpak install flathub org.freedesktop.Sdk/x86_64/18.08
```

#### clone and build flatpak from yaml
```
git clone https://github.com/fastrizwaan/tt5_flatpak.git
cd tt5_flatpak
```

copy tt5.zip to tt5_flatpak/ directory 
tt5 is also known as "Typing Tutor 5 5" 

### Then run the build

```

# build
flatpak-builder --force-clean build-dir io.github.tt.yml

# install 
flatpak-builder --user --install --force-clean build-dir io.github.tt.yml

# run
flatpak run io.github.tt.yml
```

#### Build a flatpak bundle file from the above built repo:
```
flatpak-builder --repo="repo" --force-clean "build" io.github.tt.yml
flatpak --user remote-add --no-gpg-verify "tt" "repo"
flatpak build-bundle "repo" "tt.flatpak" io.github.tt --runtime-repo="https://flathub.org/repo/flathub.flatpakrepo"

flatpak --user install tt.flatpak
flatpak run io.github.tt
```
