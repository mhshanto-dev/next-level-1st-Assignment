ভূমিকা
TypeScript-এ any, unknown এবং never নামে তিনটি বিশেষ Type রয়েছে। এগুলো সাধারণ Type-এর মতো কাজ করে না। প্রতিটির আলাদা ব্যবহার রয়েছে। তাই এগুলোর পার্থক্য জানা দরকার।
বিস্তারিত আলোচনা
any ব্যবহার করলে Variable-এর মধ্যে যেকোনো ধরনের Value রাখা যায়। এমনকি Type Check ছাড়াই সেই Value নিয়ে বিভিন্ন কাজ করা যায়। কিন্তু এতে ভুল হওয়ার সম্ভাবনা থাকে।
unknown-এর মধ্যেও যেকোনো ধরনের Value রাখা যায়। তবে এর ক্ষেত্রে আগে Type Check করতে হয়। Type নিশ্চিত না করে সরাসরি Method ব্যবহার করা যায় না।
never এমন একটি Type, যা এমন Value বোঝায় যা কখনো পাওয়া যায় না। যেমন, কোনো Function যদি সবসময় Error Throw করে, তাহলে তার Return Type never হতে পারে।
Code Example:
let value: any = "Hello";
console.log(value.toUpperCase());

let data: unknown = "Hello";

if (typeof data === "string") {
  console.log(data.toUpperCase());
}

function showError(message: string): never {
  throw new Error(message);
}
এখানে any সরাসরি ব্যবহার করা হয়েছে। কিন্তু unknown ব্যবহার করার আগে typeof দিয়ে Type Check করা হয়েছে।
কেন unknown বেশি ভালো?
আমি unknown ব্যবহার করাকে বেশি নিরাপদ মনে করি। কারণ এটি ভুল Operation করতে বাধা দেয়। বিশেষ করে API থেকে Data আসলে বা User Input গ্রহণ করলে আমরা সবসময় Data-এর Type জানি না।
উপসংহার
Data-এর Type জানা না থাকলে unknown ব্যবহার করা ভালো। অপ্রয়োজনে any ব্যবহার করা উচিত নয়। আর যেসব Function স্বাভাবিকভাবে Return করে না, সেখানে never ব্যবহার করা যায়।
