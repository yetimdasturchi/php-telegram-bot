# php-telegram-bot
[@kibertexnik](https://t.me/kibertexnik) telegram kanali uchun php tilida yozilgan telegram api kutubxona

**Ishga tushirish:**

    $settings = ['token' => 'apitokeningiz'];
    $tg = new Telegram($settings);

**Xabar yuborish:**

    $tg->set_chatId('@iplosvoy')
	   ->send_chatAction('typing')
       ->send_message('Telegram botdan salom');

**Api javobini olish:**

    $tg->result(); //Umumiy massiv
    $tg->result('kalit'); //massivdan kerakli qismni ajratib olish

**Inline keyboard qo'shish:**

    $tg->set_chatId('@iplosvoy')
	   ->send_chatAction('typing')
	   ->set_inlineKeyboard([
            [
                [
                    "text" => "Bir",
                    "callback_data" => "one"
                ],
                [
                    "text" => "Ikkin",
                    "callback_data" => "two"
                ]
            ]
        ])
       ->send_message('Inline keyboardni tekshirish');

**Reply keyboard qo'shish:**

    $tg->set_chatId('@iplosvoy')
	   ->send_chatAction('typing')
	   ->set_replyKeyboard([
            ['7', '8', '9'],
            ['4', '5', '6'],
            ['1', '2', '3'],
                ['0']
        ])
       ->send_message('Reply keyboardni tekshirish');

**Rasm yuborish:**

    $tg->set_chatId('@iplosvoy')
	   ->send_photo('rasmmanzili.png', 'Rasm tasnifi');

**Hujjat yuborish:**

    $tg->set_chatId('@iplosvoy')
	   ->send_document('rasmmanzili.pdf');

**Chat harakatlarini belgilash:**

    $tg->send_chatAction('harakat', '@iplosvoy');

 - typing
 - upload_photo
 - record_video
 - upload_video
 - record_audio
 - upload_audio
 - upload_document
 - find_location

> Fayllar yuborish jarayonida harakat *CURLOPT_PROGRESSFUNCTION* orqali avtomatik belgilanadi.

**Boshqa so'rovlar:**

    $tg->get_me();
    $tg->send_location('41.2943170', '69.354002', '@iplosvoy');
    $tg->send_contact('+998902600042', 'Manuchehr', 'Usmonov' '@iplosvoy');
    $tg->send_audio('audio.mp3', '@iplosvoy');
    $tg->send_video('video.mp4', 'Bugungi tadbir', '@iplosvoy');
    $tg->get_chatMember('@kibertexnik', '@iplosvoy');
    $tg->get_userProfilePhotos('@iplosvoy');
    $tg->get_chat('@iplosvoy');
    $tg->get_chatAdministrators('@kibertexnik');
    $tg->get_chatMembersCount('@kibertexnik');
    
