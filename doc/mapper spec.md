itemmapper

<<<<<<< Updated upstream
find(int $feedId, $userId)



findAll()

request: get just starred items of a user 
	SELECT * FROM items 
		WHERE user_id = ? AND status = ?
		(AND id < ? LIMIT ?)
		(AND items.lastmodified >= ?)

request: get all items of a user (unread and read) 
	SELECT * FROM items 
		WHERE user_id = ? AND status = ?
		(AND id < ? LIMIT ?) 
		(AND items.lastmodified >= ?)

request: get all items of a folder of a user (unread and read)
	SELECT * FROM items 
		JOIN feeds
			ON feed.id = feed_id
		WHERE user_id = ? AND status = ? AND feed.folder_id = ?
		(AND id < ? LIMIT ?)
		(AND items.lastmodified >= ?)


request: get all items of a feed of a user (unread and read)
	SELECT * FROM items 
		WHERE user_id = ? AND status = ? AND feed_id = ?
		(AND id < ? LIMIT ?)
		(AND items.lastmodified >= ?)


all requests: can be specified using an (offset (id), limit) or (updatedSince (timestamp))
=======
findAllFromUser($userId)
find(int $feedId, $userId)

findAll($status, $feedId, $userId, );
>>>>>>> Stashed changes

foldermapper

find($feedId, $userId)
<<<<<<< Updated upstream
findAllFromUser($userId)
=======
>>>>>>> Stashed changes

feedmapper

find($feedId, $userId)
findAll()
findAllFromUser($userId)
getStarredCount($userId)