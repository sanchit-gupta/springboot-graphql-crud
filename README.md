# Springboot with GraphQL Demo
The source code in this module is to support this [blog post](https://springframework.guru/using-graphql-in-a-spring-boot-application/) 

#This is a CRUD application to demo a SpringBoot and GraphQL integration. 

Examples which needs to run from postman:

http://localhost:8082/apis/graphql

all POST calls

1. --------------------------------------Fetch
{
    findAllAuthors {
        id
        name
        age
    }
}

{
    findAllTutorials {
        id
        title
        description
        author {
            id
            name
        }
    }
}

2. ----------------------------------------Create
mutation {
    createAuthor (name: "Author4", age : 44) {
        id
        name
        age
    }
}

mutation {
    createTutorial (title: "Thirsty Crow", description: "Story of thirsty crow", author: 2) {
        id
        title
        description
    }
}

3. --------------------------------------------------------Update
mutation {
    updateTutorial (id: 5, title: "Thirsty Crow 2", description: "Story of thirsty crow") {
        id
        title
        description
    }
}

4. --------------------------------------------------------Delete
mutation {
    deleteTutorial (id: 5)
}
