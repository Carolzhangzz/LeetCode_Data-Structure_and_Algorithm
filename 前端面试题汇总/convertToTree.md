// 实现 convert2Tree 方法将下面数组根据 id 和 parentId 转成树状
// 时间复杂度O(n)，root 只有一个
```js
// 示例数据
const items = [
    { id: 1, name: 'Node 1', parentId: null },
    { id: 2, name: 'Node 2', parentId: 1 },
    { id: 3, name: 'Node 3', parentId: 1 },
    { id: 4, name: 'Node 4', parentId: 2 },
    { id: 5, name: 'Node 5', parentId: 2 },
    { id: 6, name: 'Node 6', parentId: 3 },
    { id: 7, name: 'Node 7', parentId: 3 }
];

// 使用该函数转换数据
const tree = convert2Tree(items);
console.log(JSON.stringify(tree, null, 2));


function convert2Tree(items) {
    // 创建一个映射，将每个元素的 id 映射到它的元素对象
    const map = new Map();
    const roots = [];

    // 初始化映射并添加 children 数组
    items.forEach(item => {
        map.set(item.id, { ...item, children: [] });
    });

    // 将每个元素插入其父级的 children 数组中
    items.forEach(item => {
        const node = map.get(item.id);
        if (item.parentId === null || item.parentId === undefined) {
            // 没有父级元素的节点是根节点
            roots.push(node);
        } else {
            // 在父节点中插入该节点
            const parent = map.get(item.parentId);
            if (parent) {
                parent.children.push(node);
            }
        }
    });

    // 根节点列表
    return roots;
}

```