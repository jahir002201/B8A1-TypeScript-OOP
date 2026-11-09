# TypeScript এ Generics কীভাবে কাজ করে এবং Promise<T> Response এর ক্ষেত্রে কীভাবে সাহায্য করে?

## Introduction

TypeScript এর অন্যতম গুরুত্বপূর্ণ Feature হলো Generics। Generics ব্যবহার করে এমন Function, Class এবং Interface তৈরি করা যায়। বিভিন্ন Data Type এর সঙ্গে কাজ করতে পারে। এর ফলে একই Code বারবার না লিখে Reusable এবং Type safe Code তৈরি করা সম্ভব।

## Generics কীভাবে কাজ করে?

Generics এ সাধারণত `T`, `K` , `U`-এর মতো Type Parameter ব্যবহার করা হয়। Function ব্যবহারের সময় এগুলো নির্দিষ্ট Data Type গ্রহণ করে।

উদাহরণ:

```typescript

const identity = <T>(value: T) : T => {

    return value;
};

identity<number>(100);

identity<string>("Calculus");

```

এখানে `T` Input-এর Data Type নির্দেশ করে। Function যে Type-এর Value গ্রহণ করে। একই Type-এর Value Return করে। ফলে `any` ব্যবহার না করেই বিভিন্ন Data Type নিয়ে কাজ করা যায়।

Array-এর ক্ষেত্রেও Generics ব্যবহার করা যায়।

```typescript

const getFirstItem = <T>(items: T[]) : T => {

    return items[0];
};

getFirstItem<number>([10, 20, 30]);
getFirstItem<string>(["React", "Django" "Laravel", "TypeScript"]);

```

এখানে Function টি নির্দিষ্ট Type এর Array গ্রহণ করে আর সেই Type এর প্রথম Element Return করে।

## Generics-এর সঙ্গে Promise<T>

Promise হলো JavaScript এর একটি Feature যা async Operation এর পাওয়া Result নির্দেশ করে। TypeScript এ `Promise<T>` ব্যবহার করে Promise সফলভাবে সম্পন্ন হলে কী ধরনের Value Return করবে তা নির্ধারণ করা যায়।

উদাহরণ:

```typescript

const calculateSquare = async (number: number) : Promise<number> => {

    return number * number;
};

```

এখানে `Promise<number>` বোঝায় Function টি সফলভাবে সম্পন্ন হলে একটি Number Value দিয়ে Resolve হবে।

Generics এবং Promise একসঙ্গে ব্যবহার করে Reusable async function তৈরি করা যায়।

```typescript

const fetchData = async <T>(data: T): Promise<T> => {

    return data;
};

fetchData<string>("User Data");

fetchData<number>(250);

```

এই Function বিভিন্ন Data Type গ্রহণ করতে পারে এবং একই Type এর Promise Return করে। ফলে Type Safety বজায় থাকে এবং ভুল Data Type ব্যবহারের ঝুঁকি কমে।

## Conclusion

Generics TypeScript এ Reusable, Flexible এবং Type safe Code লেখার সুযোগ তৈরি করে। অন্যদিকে `Promise<T>` async Programming এ Result এর Type নির্দিষ্ট করে। দুটি Feature একসঙ্গে ব্যবহার করলে Application আরও Organized, Reliable, Scalable এবং Maintainable হয়।