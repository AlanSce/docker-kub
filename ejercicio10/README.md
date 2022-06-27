Primero probé que funcionase la comunicación con el bot corriéndolo como contenedor de docker: 

```
docker run -d --name bot -e TELEGRAM_TOKEN=<token> nicopaez/telegrambot:0.0.7
```

Borré el contendor luego de la prueba. 

Luego copié el deployment del ejercicio 9, y realicé las modificaciones que creí necesarias. 

Apliqué el deployment con 

```
kubectl apply -f deployment.yaml
```

Y realicé la prueba de enviarle "/version" al bot. 

Verifiqué con el comando `kubectl logs` la salida del pod: 

```
(master) alan@alan-vb:~/repo/docker-kub/ejercicio10$ kubectl get pods
NAME                   READY   STATUS              RESTARTS   AGE
bot-7fd5dc7885-mh8vp   0/1     ContainerCreating   0          25s


(master) alan@alan-vb:~/repo/docker-kub/ejercicio10$ kubectl logs bot-7fd5dc7885-mh8vp
I, [2022-06-27T02:25:45.445093 #1]  INFO -- : Starting bot version:0.0.7
I, [2022-06-27T02:25:45.445271 #1]  INFO -- : token is 5526556281:AAF6tNvX3UWsOIRNr02esVCLCWCqLEvMcwg
I, [2022-06-27T02:25:45.445332 #1]  INFO -- : Starting bot
I, [2022-06-27T02:26:37.815213 #1]  INFO -- : Incoming message: text="/version" uid=911322056
D, [2022-06-27T02:26:37.815480 #1] DEBUG -- : From: @Alan_Scelza, message: #<Telegram::Bot::Types::Message:0x0000560f2c4254f0 @message_id=7, @from=#<Telegram::Bot::Types::User:0x0000560f2c3f45d0 @id=911322056, @is_bot=false, @first_name="Alan", @last_name="Scelza", @username="Alan_Scelza", @language_code="en">, @chat=#<Telegram::Bot::Types::Chat:0x0000560f2c3f0570 @id=911322056, @first_name="Alan", @last_name="Scelza", @username="Alan_Scelza", @type="private", @title=nil, @all_members_are_administrators=nil, @photo=nil, @description=nil, @invite_link=nil, @pinned_message=nil>, @date=1656296797, @text="/version", @entities=[#<Telegram::Bot::Types::MessageEntity:0x0000560f2c416a68 @offset=0, @length=8, @type="bot_command", @url=nil, @user=nil>], @forward_from=nil, @forward_from_chat=nil, @forward_from_message_id=nil, @forward_signature=nil, @forward_sender_name=nil, @forward_date=nil, @reply_to_message=nil, @edit_date=nil, @media_group_id=nil, @author_signature=nil, @caption_entities=[], @audio=nil, @document=nil, @animation=nil, @game=nil, @photo=[], @sticker=nil, @video=nil, @voice=nil, @video_note=nil, @caption=nil, @contact=nil, @location=nil, @venue=nil, @poll=nil, @new_chat_members=[], @left_chat_member=nil, @new_chat_title=nil, @new_chat_photo=[], @delete_chat_photo=nil, @group_chat_created=nil, @supergroup_chat_created=nil, @channel_chat_created=nil, @migrate_to_chat_id=nil, @migrate_from_chat_id=nil, @pinned_message=nil, @invoice=nil, @successful_payment=nil, @connected_website=nil>
```
