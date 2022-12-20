CREATE TABLE IF NOT EXISTS singers(
	singer_id SERIAL primary key,
	nickname varchar(80) not null
);

CREATE TABLE IF NOT EXISTS styles(
	style_id SERIAL primary key,
	name varchar(50) not null
);

CREATE TABLE IF NOT EXISTS albums(
	album_id SERIAL primary key,
	name varchar(50) not null,
	year integer
);

CREATE TABLE IF NOT EXISTS collections(
	collection_id SERIAL primary key,
	name varchar(50) not null,
	year integer
);

CREATE TABLE IF NOT EXISTS tracks(
	track_id SERIAL primary key,
	name varchar(50) not null,
	duration integer,
	album_id integer not null references albums(album_id)
);

CREATE TABLE IF NOT EXISTS tracks_collections(
	collection_id integer not null references collections(collection_id),
	track_id integer not null references tracks(track_id),
	CONSTRAINT tracks_collections_pk PRIMARY KEY (collection_id, track_id)
);

CREATE TABLE IF NOT EXISTS singers_albums(
	album_id integer not null references albums(album_id),
	singer_id integer not null references singers(singer_id),
	CONSTRAINT singers_albums_pk PRIMARY KEY (album_id, singer_id)
);

CREATE TABLE IF NOT EXISTS singers_styles(
	style_id integer not null references styles(style_id),
	singer_id integer not null references singers(singer_id),
	CONSTRAINT singers_styles_pk PRIMARY KEY (style_id, singer_id)
);
