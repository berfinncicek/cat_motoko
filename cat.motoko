import Trie "mo:base/Trie";
import Text "mo:base/Text";
import Nat32 "mo:base/Nat32";
import Bool "mo:base/Bool";
import Option "mo:base/Option";

actor {

  type CatId = Nat32;
  type Cat = {
    name : Text;
    age : Nat32;
    breed : Text;
    isAdopted : Bool;
  };

  type ResponseCat = {
    name : Text;
    age : Nat32;
    breed : Text;
    isAdopted : Bool;
    id : Nat32;
  };

  private stable var nextCatId : CatId = 0;

  private stable var cats : Trie.Trie<CatId, Cat> = Trie.empty();

  public func addCat(cat : Cat) : async Text {
    let catId = nextCatId;
    nextCatId += 1;
    cats := Trie.replace(
      cats,
      key(catId),
      Nat32.equal,
      ?cat,
    ).0;
    return "Cat Added Successfully";
  };

  public func updateCat(catId : CatId, cat : Cat) : async Bool {
    let result = Trie.find(cats, key(catId), Nat32.equal);
    let exists = Option.isSome(result);
    if (exists) {
      cats := Trie.replace(
        cats,
        key(catId),
        Nat32.equal,
        ?cat,
      ).0;
    };
    return exists;
  };

  public func deleteCat(catId : CatId) : async Bool {
    let result = Trie.find(cats, key(catId), Nat32.equal);
    let exists = Option.isSome(result);
    if (exists) {
      cats := Trie.replace(
        cats,
        key(catId),
        Nat32.equal,
        null,
      ).0;
    };
    return exists;
  };

  
  public func adoptCat(catId : CatId) : async Bool {
    let result = Trie.find(cats, key(catId), Nat32.equal);
    let exists = Option.isSome(result);
    if (exists) {
      switch result {
        case (?cat) {
          let adoptedCat = { name = cat.name; age = cat.age; breed = cat.breed; isAdopted = true };
          cats := Trie.replace(
            cats,
            key(catId),
            Nat32.equal,
            ?adoptedCat,
          ).0;
        };
        case _ {};
      }
    };
    return exists;
  };

  private func key(x : CatId) : Trie.Key<CatId> {
    return { hash = x; key = x };
  };

};
