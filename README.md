# General


To use user-friendly tools, an API for interaction with the editing server was developed independently.

The editor is available only if the address selected in MetaMask as the main address for the site https://editor.canvaisland.art/ is the owner of any sector. After authorization, the editing console becomes available through the API and sector preview. Apart from the owner of the sector, no one sees the sector before publication.

The editor API is built on GraphQL. If you are not familiar with this concept, you can easily find information on the Internet ( https://graphql.org/ ) .

#Commands

In the editing console, 2 types of server commands (API calls) are available for you: Query - to get data and Mutation - to change data. When writing commands, don't forget to use ctrl+spacebar - to bring up a list of hints
Press to execute commands 

You can see a list of your sectors with the following query:


query{
sectors{
 	_id
 	name
  }
}


You can find a detailed description of requests and response formats in the API documentation (in the console, on the left, the button ).
 
	
To change data, you need to use Mutations. For example, to create 1 block of voxels, the following command is used (in the token parameter, specify the token of the sector in which you want to make changes):
mutation{
  sector(token:"5509…8225"){
    voxels{
      add(data:{
        position:{x:0, y:7, z:0},
        material:255,
        brush:0})
    }
  }
}

 

After making some changes through the commands, you need to reload the sector display page (3D preview). After commands to change voxels, this is not required, changes are displayed without reloading.

  

A description of the parameters used can be found in the API documentation (see above)
	It should be clarified that the 'brush' parameter indicates a brush - a preset set of voxels. What these sets look like is shown in the table below:
  
  
  
