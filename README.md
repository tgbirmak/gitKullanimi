
# Github Notları

## git init
## git add
## git commit -m "First Commit"
## git log
## git log -n 3 (sadece üçüncü satırı göster) 
## git commit --amend -m "Master2 | Bu amendle eklenmiş bir commit" ---> Commit eklemeden, son commite dahil etme
## git revert commitID ---> 395049064 en az 7 tane karakteri kopyala yapıştır---> son yapılan değişikler çalışmadan da geri alınır. 
## revert'ün revertü yapılabilir.
## git reset --hard 93085943085 commitleri ID ye göre siler. (HEAD diğer kalan commit olur)

## git diff ea23c0195c26ea9c3444e1238227e53ec6fe97d3..064b3f54dcd8ac8573a8b68984eb0bcbd19acab9 index.md

## git branch ---> varolan branchler
## git branch header ---> "header" adında bir branch oluştur.

## git checkout -b footer
Switched to a new branch 'footer' ---> hem "footer" adında branch oluşturdu hem de onu aktif etti.

## git checkout master --> "master" branch ine geç.
## git branch -D footer ---> "footer" branchini sildi.
## git checkout master---> "header" branchindeki dosyaları göstermez. Sadece master branchindekileri gösterir
## git checkout header --> headerdaki dosyalara geçer.

## git touch footer.md ---> md dosyasını oluşturur
## git checkout -b ile oluşturulan branchler, mevcut branch imizi referans alır.
## git stash ---> commit öncesi değişiklileri kaydeder.
## git stash list --> bu değişiklikleri listeler.
## git stash pop ---> değişiklikleri başa alır.Stash listten kaldırır.
## git stash apply --> geri alır, stash listten kaldırmaz
## git merge header  --> master branchindeyken header branchi üzerindeki değişiklikleri ekledi. Headerda yapılan Commitleri de ekledi.

## (BU NEDENLE COMMİTLERİN BAŞINDA BRANCH İSMİ VE SIRASI YAZMALI. "Header 1 | birinci değişiklik gibi")

## git merge ile birleşimlerde, birleşimler commitle bildirilmez. Diğer takım arkadaşları birleştirmeyi anlamaz.

## git merge --squash footer,
## git rebase -- sadece bir katılım yapıyor. Değişiklikleri alıyor.
    git commit -m "Footer MAster ile birleştirildi"
https://aliozgur.gitbooks.io/git101/content/remote_repositoryler/remote_degisiklikleri_entegre_etmek.html


git fetch komutu ile remote branch'deki değişiklikleri indirdikten sonra ise git log komutunu kullanarak bu remote branch'deki değişiklikler ile ilgili bilgileri görebiliriz. (değişiklik tarihi, kimin yaptığı, değişen dosyalar ve commiti sırasında girilen mesaj gibi)

Değişiklikleri inceledikten sonra bunları local branch'inize entegre etmeye karar verdiğimizde ise git pull komutunu kullanmamız gerekecek

Remote branchdeki değişikliklerin bilgilerini indirmek için kullanılan fetch (türkçe anlamı getirmek) ve bu değişiklikleri entegre etmek için kullanılan pull (türkçe anlamı çekmek) ifadelerinin birbirine yakın anlamları olduğu için karıştırabilirsiniz. Bu karışıklığın önüne geçmek için yapacağınız en güzel şey git pull komutunu hiç kullanmamak olacaktır. Ayrıntılar için İngilizce bir blog post olan Git: fetch and merge, don't pull inceleyebilirsiniz.

Git pull komutu aslında arka arkaya iki şey yapmanızı sağlar

Remote branch'deki değişiklikler ile ilgili bilgileri indirmek, yani git fetch
Remote branch'deki değişiklikleri local branch'inize entegre etmek yani git merge
İlerleyen bölümlerde çakışmaların tespit edilmesi, çözülmesi ve değişikliklerin entegre edilmesi konularını ayrıntılı olarak ele alacağız şimdilik sadece iş akışımızı özetleyip bu konuyu burada sonlandıralım. Akışımız özetle şöyle olacak

git fetch : remote'dan güncelleme bilgilerini indir
git diff : remote ve local arasındaki farkları incele
git merge : değişiklikleri otomatik merge et çakışma varsa bir sonraki adıma geçin
Çakışma olan dosyalarınızı açın ve çakışmaları düzeltin
git add: çakışmanın giderildi ve değişiiklik Staging Area'ya alındı

# Remote 'a yükleme ---> git remote add origin https://github.com/tgbirmak/gitKullanimi.git

                                # git remote -v
                                # git add .
                                # git commit -m "Add existing file"
                                # git push origin master


# nickname of repo default --> origin


git pull --allow-unrelated-histories <nick name of repository> <branch name>

like:

git pull --allow-unrelated-histories origin master

# upstream kavramı

The -u flag is specifying that you want to link your local branch to the upstream branch. This will also create an upstream branch if one does not exist. None of these answers cover how i do it (in complete form) so here it is:

git push -u origin <your-local-branch-name>
So if your local branch name is coffee

git push -u origin coffee

git branch -m swift main
git fetch origin
git branch -u origin/main main
git remote set-head origin -a
