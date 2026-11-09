# TypeScript এ Type Alias এবং Interface এর মধ্যে পার্থক্য কী?

## Introduction

TypeScript এ নিজস্ব বা Custom Type তৈরি করার জন্য Type Alias এবং Interface সাধারণত Object এর structure নির্ধারণে ব্যবহৃত হয়। দুটিই Data এর structure নির্ধারণ করতে এবং Code এর Type safety বজায় রাখতে সাহায্য করে। তবে এদের ব্যবহারের ক্ষেত্রে কিছু পার্থক্য রয়েছে।

## Type Alias কী?

Type Alias তৈরি করতে `type` Keyword ব্যবহার করা হয়। এর মাধ্যমে Primitive, Object, Union এবং Intersection Type তৈরি করা যায়।

উদাহরণ:

```typescript

type Student = {
    name: string;
    age: number;
};

type MathResult = number | string;

```

এখানে `Student` একজন শিক্ষার্থীর তথ্য নির্ধারণ করেছে। অন্যদিকে, `MathResult` Number অথবা String Value গ্রহণ করতে পারবে।

## Interface কী?

Interface তৈরি করতে `interface` Keyword ব্যবহার করা হয়। এটি সাধারণত Object এর structure নির্ধারণ করতে ব্যবহৃত হয়।

উদাহরণ:

```typescript

interface Developer {
    name: string;
    skill: string;
}

interface FullStackDeveloper extends Developer {
    experience: number;
}

```

এখানে `FullStackDeveloper`, `Developer` Interface-এর Property গুলো Inherit করেছে। Interface এ `extends` ব্যবহার করে Inheritance করা যায়। একই নামে একাধিক Interface তৈরি করলে সেগুলো একত্রিত হয়। একে Declaration Merging বলা হয়।

## মূল পার্থক্য

Type Alias দিয়ে Primitive, Union, Intersection এবং Object Type তৈরি করা যায়। অন্যদিকে, Interface সাধারণত Object এর structure নির্ধারণে ব্যবহৃত হয়। Interface এ `extends` আর Type Alias এ `&` ব্যবহার করে একাধিক Type একত্রিত করা যায়। Type Alias-এ `=` ব্যবহার করা হয়, কিন্তু Interface Declaration-এ `=` ব্যবহার করা হয় না।

## কখন কোনটি ব্যবহার করবেন?

Object Structure, Class Contract এবং Declaration Merging প্রয়োজন হলে Interface ব্যবহার করা ভালো। অন্যদিকে, Union, Primitive এবং Complex Type তৈরি করতে Type Alias বেশি সুবিধাজনক।

## Conclusion

Type Alias এবং Interface দুটিই TypeScript এর গুরুত্বপূর্ণ Feature। কোন পরিস্থিতিতে কোনটি ব্যবহার করতে হবে তা বুঝতে পারলে Code আরও Organized, Reusable, Scalable এবং Maintainable করা সম্ভব।