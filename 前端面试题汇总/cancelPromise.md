// 问题三：
// 实现一个可取消的 Promise，效果如下：
```js
const res = new CancellablePromise((resolve, reject) => {
  setTimeout(() => {
    // do something
    resolve();
  }, 1000);
}).then(() => {
  console.log('done');
}).catch(() => {
  console.log('done');
});
```

```js
class CancellablePromise {
    constructor(executor) {
        this.cancelled = false;
        this.promise = new Promise((resolve, reject) => {
            this.cancel = () => {
                this.cancelled = true;
                reject(new Error('Cancelled'));
            };
            executor(resolve, reject);
        });
    }

    then(onFulfilled, onRejected) {
        return this.promise.then(
            value => !this.cancelled && onFulfilled(value),
            reason => !this.cancelled && onRejected(reason)
        );
    }

    catch(onRejected) {
        return this.promise.catch(reason => !this.cancelled && onRejected(reason));
    }

    stop() {
        // 不执行任何操作，取消的时候已经在 cancel 方法中处理了
    }
}
```
Promise 是 JavaScript 中用于处理异步操作的一种机制。它代表了一个异步操作的最终完成或失败，并且可以方便地对异步操作进行链式调用。Promise 有三种状态：pending（等待中）、fulfilled（已完成）和rejected（已拒绝）。




