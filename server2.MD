## Queries

### Course

#### Query
```
query getSingleCourse($courseID3: Int!, $test: String) {
    course(id: $courseID3, test: $test) {
        title
        author
        description
        url
    }
}
```

#### Query Variables
```
{
  "courseID3": 1,
  "test": "test text"
}
```

### Courses

#### Query
```
query getCourses($courseTopic: String) {
    courses(topic: $courseTopic) {
        title
        author
        topic
    }
}
```

#### Query Variables
```
{
  "courseTopic": "JavaScript"
}
```

### With Fragments

#### Query
```
query getCourseWithFragments($courseID1: Int!, $courseID2: Int!) {
      course1: course(id: $courseID1) {
             ...courseFields
      },
      course2: course(id: $courseID2) {
            ...courseFields
      } 
}
fragment courseFields on Course {
  title
  author
  description
  topic
  url
}
```

#### Query Variables
```
{ 
  "courseID1":1,
  "courseID2":1
}
```

### Mutations

#### Query
```
mutation updateCourseTopic($id: Int!, $topic: String!) {
    updateCourseTopic(id:$id, topic:$topic) {
        id
        title
        author
        topic
    }
}
```

#### Query Variables
```
{
  "id": 1,
  "topic": "new topic"
}
```
