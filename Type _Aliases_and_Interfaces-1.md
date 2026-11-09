ভূমিকা
TypeScript-এ type এবং interface ব্যবহার করে Data-এর Structure তৈরি করা যায়। দুটির কাজ অনেকটা একই রকম হলেও কিছু পার্থক্য রয়েছে। কোনটি ব্যবহার করব, তা আমাদের কাজের ওপর নির্ভর করে।
বিস্তারিত আলোচনা
interface সাধারণত Object-এর Structure তৈরি করতে ব্যবহার করা হয়। একটি Interface অন্য Interface থেকে extends ব্যবহার করে Property নিতে পারে। এর আরেকটি সুবিধা হলো Declaration Merging। অর্থাৎ একই নামের একাধিক Interface থাকলে TypeScript সেগুলো একসঙ্গে যুক্ত করতে পারে।
অন্যদিকে, type দিয়ে শুধু Object নয়, String, Number, Union, Intersection এবং Tuple-এর মতো Type তৈরি করা যায়। তবে একই নামের একাধিক Type Alias তৈরি করে Interface-এর মতো Merge করা যায় না।
Code Example:
interface User {
  name: string;
  age: number;
}

interface Admin extends User {
  role: string;
}

type Status = "active" | "inactive";
এখানে Admin Interface, User থেকে Property নিয়েছে। আর Status শুধু দুটি নির্দিষ্ট String Value গ্রহণ করতে পারবে।
কখন কোনটি ব্যবহার করব?
Object-এর Structure তৈরি করতে আমি সাধারণত interface ব্যবহার করি। আর Union, Intersection বা অন্য ধরনের Complex Type তৈরি করতে type ব্যবহার করি।
উপসংহার
type এবং interface দুটিই গুরুত্বপূর্ণ। কোনটি ভালো, তা নির্ভর করে কাজের ধরনের ওপর। কোড সহজে বোঝা যায় এমনভাবে ব্যবহার করাই সবচেয়ে ভালো।
