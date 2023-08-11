@startuml
set namespaceSeparator ::

class "Artist" {
  +int? id
  +String firstName
  +String lastName
  +String alias
  +String coolSentence
}

class "Album" {
  +int? id
  +String name
  +DateTime creationDate
  +String? coverPath
}


class "ProjectVersion" {
  +int? id
  +String name
  +String content
  +DateTime creationDate
  +DateTime lastEdit
  +IsarLink<Artist> author
  +IsarLinks<Artist> coauthors
  +TextSettings textSettings
  +IsarLink<ProjectMetronome> metronome
  +IsarLinks<Track> tracks
}


"Project" o-- "ProjectVersion"
"Project" o-- "Content"

class "Project" {
  +int? id
  +String name
  +String content
  +IsarLink<Content> content
  +IsarLink<ProjectVersion checkedOutVersion
  +IsarLinks<ProjectVersion> versions
  +DateTime creationDate
  +DateTime lastEditedDate
  +IsarLinks<Album> albums
}

class "Content" {
  +int? id
  +IsarLinks<LyricsFragment> lyricsFragments
}

class "LyricsFragment" {
  +int index
  +Beat beat
  +Chord chord
  +IsarLinks<TextFragment> text
}

"LyricsFragment" o-- "TextFragment"
class "Beat" {
    +int duration
    +double bars
}

class "Chord" {
    + String value
}
class "TextFragment" {
  +String textContent
  +tag tag
}

enum "tag" <<enum>> {
    +normal
    +bold
    +italic
}


"TextFragment" o-- "tag"
class "Track" {
  +int? id
  +IsarLinks<AudioFile> audioFiles
  +int maxBoundary
  +dynamic initAll()
  +dynamic pauseAll()
  +dynamic play()
  +dynamic prepareInsert()
}


class "TextSettings" {
  +int? id
  +int fontSize
}

class "ProjectMetronome" {
  +int? id
  +int beatsPerBar
  +int beatsPerMinute
  +bool enabled
}

class "apollo::core::src::models::src::record.dart::ApolloRecord" {
  +int leftBoundary
  +String path
  +String name
  -Record? _recorder
  +dynamic init()
  +dynamic start()
  +dynamic stop()
}

"apollo::core::src::models::src::record.dart::ApolloRecord" o-- "record::src::record.dart::Record"

class "apollo::core::src::models::src::user.dart::User" {
}


class "AudioFile" {
  +int? id
  +String path
  +AudioFileStatus state
  +int leftBoundary
  +int rightBoundary
  +int initLeftBoundary
  +int initRightBoundary
  +AudioPlayer player
  +int duration
  +int leftOffset
  +dynamic autosetRightBoundary()
  +dynamic initPlayer()
  +dynamic move()
}

"AudioFile" o-- "AudioFileStatus"
"AudioFile" o-- "just_audio::just_audio.dart::AudioPlayer"

class "AudioFileStatus" {
  +int index
  {static} +List<AudioFileStatus> values
  {static} +AudioFileStatus loaded
  {static} +AudioFileStatus unloaded
  {static} +AudioFileStatus errored
}

"AudioFileStatus" o-- "AudioFileStatus"

@enduml