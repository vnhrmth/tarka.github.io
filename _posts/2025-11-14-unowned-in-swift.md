# Unowned in Swift

What is the meaning of `unowned` in Swift and why would someone use this keyword?

---

## Scenario
Consider I have an object called **John** created in Swift, and that can be passed around another object of type **Car**, maybe called **Bugatti**.

- Bugatti has an owner: John  
- John has a car: Bugatti  

Everything is fine till now, but now if you think, there are questions like:

- **Does every car have an Owner?**  
  Yes, there will be a definite owner to every car, either it can be an entity or a person.

- **Does every owner have a Car?**  
  No, there are people who don't own a car and can either yes or no.

---

## Ownership Design
We solved a major criteria in our class design: the ownership part.

In general, we translate this to:

- **Car (Bugatti)** has a **strong relationship** with the **Owner (John)**  
- **Owner (John)** has a **weak relationship** with the **Car (Bugatti)**  

So basically, we would need this so that whenever John doesn't exist in memory, Car too doesn't need to be in memory so that it can be freed for other purposes.

---

## Analogy
Consider you are holding a dog on a leash and then your friend asks to hold the dog, but if you never come back, the dog will continue to be leashed and will never be released.  
Our goal is to release the dog so the memory is freed whenever we don't require it anymore.

This is a basic understanding to keep the memory for re-use for other purposes rather than storing unnecessary data in memory, which helps in faster apps.

---

## Solution
So how can we solve this freeing memory concept?  
We can use something called **`weak`** and **`unowned`** for weak relationships that need to be relinquished if they don't exist in memory.

- `weak` does the same as above.
- However, `unowned` is slightly different:  
  We assume that the object will always exist in lifetime where it is required, so we don't add the additional guard logic.  
  But this comes with a risk—like all assumptions cannot be true, we can't assume the object can continue to stay in memory forever.

---

### ✅ Summary
- Use `weak` when the object **may disappear**.  
- Use `unowned` when the object **must exist** during the lifetime of the reference.
