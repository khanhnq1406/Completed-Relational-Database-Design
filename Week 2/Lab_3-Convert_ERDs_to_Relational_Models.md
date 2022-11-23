# ERD 1

<img src="https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/kpzq-eJwTtqc6vnicM7a4Q_69ff374be0db46329896bc5ae4902af1_Screen-Shot-2022-01-18-at-6.07.59-PM.png?expiry=1667952000000&hmac=xUWakPI4J88WxpTQ55lqJVudv5TJOX76M_MAPqdJ4yg">

Locations(<u>ID</u>, State, City, Street, ZipCode, Country)

Galleries(<u>GalleryNum</u>, Name, Phone, Hours, Introduction, ID(fk))

Drawings(<u>DrawingNum</u>, Title, Size, Material, Date, GalleryNum(fk))

Artists(<u>ArtistNum</u>, Name, Phone, Birthday, Email)

Artists_Artists(<u>ArtistNum(fk)</u>, <u>FriendOfArtistNum(fk)</u>)

Drawings_Artists(<u>DrawingNum(fk)</u>, <u>ArtistNum(fk)</u>)

# ERD 2

<img src="https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/QW0sG5dvT82tLBuXb0_Nbg_9d8d53e343a6420994aa803ddbfe25f1_Screen-Shot-2022-01-18-at-6.08.08-PM.png?expiry=1667952000000&hmac=00YK32ohlru4G4AyjtpXxDqXvP-4kFbrOOHRToR3s5k">

Locations(<u>ID</u>, State, City, Street, ZipCode, Country, GalleryNum(fk))

Galleries(<u>GalleryNum</u>, Name, Phone, Hours, Introduction)

Drawings(<u>DrawingNum</u>, Title, Size, Material, Date, GalleryNum(fk), ArtistNum(fk))

Artists(<u>ArtistNum</u>, Name, Phone, Birthday, Email, ReferredArtistNum(fk))
