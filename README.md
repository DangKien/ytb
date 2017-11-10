composer require dangtrungkien/ytb:dev-master
thêm vào app
'providers' => [
    ...
    DangKien\Youtube\YoutubeServiceProvider::class,
],

'aliases' => [
    ...
    'Youtube' => DangKien\Youtube\Facades\Youtube::class,
],

chạy
php artisan vendor:publish --provider="DangKien\Youtube\YoutubeServiceProvider"

 redirect URI GG
http://dường dẫn app/youtube/callback 

$video = Youtube::upload($dường dẫn, [
    'title'       => 'Tiêu đề video',
    'description' => 'mô tả',
    'tags'	      => ['tag1', 'tag2', 'tag3'],
    'category_id' => 10 (id loại video)
]);

return $video->getVideoId();


tạo thumbnail

$fullpathToImage = storage_path('app/public/thumbnail.jpg');

$video = Youtube::upload($dường dẫn, $params)->withThumbnail($dường dẫn đến ảnh);

return $youtube->getThumbnailUrl();
