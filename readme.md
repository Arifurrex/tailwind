# tailwind

## tailwind setup

1.

```sh
     npm init
```

or

```sh
  npm init -y
```

for initiallize a node project .package.json file create হবে

2.

```sh
    npm i -D tailwindcss
```

npm i mean initialize -D mean developer . install a tailwindcss dependency in developer mode। node_modules file create হবে

3. install

```sh
     https://marketplace.visualstudio.com/
```

this pluging

4. ```sh
        npx tailwindcss init
   ```

   এর মদ্যমে tailwind.config.js নামে file create হবে

5. src এবং output নামে file create করব
   tailwind এর কাজ গলো আমরা src এর মদ্যে করব
   output folder এ compailer এর মদ্যমে vanilla css compile করে দিবে
   in src file i will create tailwind.css file . src/tailwind.css . any name হতে পারে

6. tailwind.css file এর মদ্যে

- @tailwind base;
- @tailwind components;
- @tailwind utilities;
  লিখব

@tailwind css er কোন property না । এখানে @ কে বলা হয় directive । যখন আমরা tailwind.css file টা tailwind এর compailer দিয়ে compile করব তখন এই derective গলো দেখে tailwind বুজতে পারবে এখানে tailwind এর base style ইনপুট করা আছে । এখানে tailwind এর components style ইনপুট আছে । এখানে tailwind এর utilities ফাইল ইনপুট করা আছে

7. root folder এর মদ্যে .vscode ফোল্ডার নিব । তার মদ্যে setting.json ফাইল create করব .এটা হল vscode এর custome code লেখার ফাইল । যেহেত tailwind এর কোড গলো vscode চিনতে পারবে না তাই যাতে warning না দেখায় তাই

```sh
    {"css.validate" : flase;"tailwindCSS.emmetCompletaions" :true;}
```

এই কোড লিকতে হবে

8. package.json ফাইল এ

   ```sh
   "scripts": {
   "build":"tailwindcss -i ./src/tailwind.css -o ./output/tailwind.css -w"
   },
   ```

   এখানে -i হল input -o output ফাইল -w হল watch

index.html এ ./output/tailwind.css ফাইল টা html ইনক্লুড করে দিব
almost done

9. ```sh
         npm run build
   ```
   দিলে tailwind build হবে

## utility and component

utility মানে individual গ্যাস বিল কিংবা ইলেকট্রিক বিল এগোল । utility মানে কাজের বস্তু

multiple utility মিলে component create হয়

tailwind হল utility base framework আর boostrap হল component base css framework । example : boostrap এ আমাদের card বানান অবস্তই দেয়া হয় । boostap এ সদুমাত্র card বললেই boostrap আমদের কার্ড বানিয়ে দেয়

tailwind এ কার্ড আমদের বানাতে হয় utility css দিয়ে

## handling hover,focus and other states

## dark mood

in tailwind.config.js file

```sh
  darkMode: 'media',
```

darkMode media মানে system device অনুসারে backgound change হবে

```sh
  darkMode: 'class',
```

class অনুসারে background change হবে

## @apply

```sh

<button
        class="px-4 py-1 border border-purple-200 rounded-full text-sm text-purple-600 font-semibold hover:text-white hover:bg-purple-600 hover:border-transparent focus:outline-none focus:ring-2 dark:text-purple-600 dark:focus:ring-offset-gray-800 dark:focus:border-transparent"
      >
        click here
      </button>

```

in src/tailwind.css file e

```sh

@tailwind base;
@tailwind components;
@tailwind utilities;

/* group utility */

.btn-purple {
  @apply px-4 py-1 border border-purple-200 rounded-full text-sm text-purple-600 font-semibold hover:text-white hover:bg-purple-600 hover:border-transparent focus:outline-none focus:ring-2 dark:text-purple-600 dark:focus:ring-offset-gray-800 dark:focus:border-transparent;
}

```
