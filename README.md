# Solidity-Exercises


<h2>1. </h2>

// SPDX-License-Identifier: MIT         
pragma solidity ^0.6.0;                     
pragma experimental ABIEncoderV2; 

import './Logger.sol' as logger;                // import de ./Logger.sol

contract SolidityCourse is logger.Logger {      // Declaration du contract
    address private owner;

    constructor() public {
        owner = msg.sender;
    }

    function whoIsOwner() public returns(address) { //  cette fonction va appeler la foncton log()  et afficher l'adress de la personne actuellement connecté qui sera le owner  du contrat
        log();
        return owner;
    }

    function getLastVisitor() public returns(address) { // cette fonction va afficher  le dernier visiteur en appeleant la fonction getLast() qui est en interne donc pas visible  et affiche encore dans un second temps l'adress du owner en appeleant log()
        address lastVisitor = getLast();
        log();
        return lastVisitor;
    }

    function getNthVisitor(uint _pos) public returns(address) {// la fonction appel getVisitorByPosition(_pos) et afiche la position de l'adresse des visiteurs   dans le tableau par ordre de connection avec l'adress du owner toujours affiché
       address nthVisitor = getVisitorByPosition(_pos);
        log();
        return nthVisitor;
    }

    function getAllVisitors() public view returns(address[] memory) { // function que seul le owner pourra appleler elle nous retournera toutes les adress des visiteurs
        require(owner == msg.sender, 'Only owner can use this function.');

        return getAll();
    }
}

<h2>2.3.4.5.</h2>

pragma solidity ^0.6.0;                     
pragma experimental ABIEncoderV2; 

contract calc {
    
    
   /// @title A contract to calculate numbers
   
    address private owner;

    constructor() public {
        owner = msg.sender;
        
    }
    
    modifier onlyOwner () {
  require(msg.sender == owner,'Only owner can use this function.');
  
  /// @dev This fonction can only be use by the owner of this contract
  _;
}
    
    function add(uint a,uint b) public pure returns(uint) {
      ///  @dev Two props in each function
      /// @notice
       uint result = a + b;
        /// @notice add those two numbers
        return result;
        
    }
    
    function sub(uint a,uint b) public pure returns(uint) {
        uint result = a - b;
        /// @notice Substract those numbers
        return result;
    }
    
    function mul(uint a,uint b) public pure returns(uint) {
        uint result = a * b;
      ///  @notice Multiply those numbers !

        return result;
    }
    
    function div(uint a,uint b) public pure returns(uint) {
        uint result = a / b;
        ///  @notice  Divide those numbers !
        return result;
        
    }
    
   
 
    
   }

// fonction declré pure : ça signifie que l'on a pas accés auw données de l'application dans notre cas ci present elle retourne une valeur qui dépend uniquement  de ses arguments elle est donc considére comme "pure"

// fonction déclaré vew : elle ne change auccune valeur et n'ecrit rien  elle se contente de lire elle ne modifie pas l'etat donc on la considere comme  "view"


<h2>6.</h2>


<div>
  <p>
  pragma solidity ^0.6.0;                     
pragma experimental ABIEncoderV2; 

contract maxInfo {
    struct  Person{
  uint age;
  string name;
  string lastname;

}

}
</p>
</div>
