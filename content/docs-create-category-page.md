---json
{
    "slug": "docs-create-category-page",
    "layout": "docs-item.html",
    "category": "document.category",
    "tag": [],
    "title": "Page of the Category",
    "title-vn": "Trang Danh Mục",
    "description": "",
    "description-vn": "### Tạo Trang Danh Mục\n* Các trường thông tin cho phép thay đổi của một Danh Mục (được giải thích trong hướng dẫn phía trước)\n```\n{\n    children: [],\n    parent: 'parent-category',\n    href: 'url',\n    files: [],\n    category: '',   \n\n    \"sortBy\": \"date\",\n    \"reverse\": false,\n    \"metadata\": {\n    \t\"name\" : \"Configuration\"\n    },\n    \"displayName\": \"document.configuration\",\n    \"perPage\": 12,\n    \"noPageOne\": true,\n    \"layout\": \"default.category.html\",\n    \"first\": \":categoryPath/index.html\",\n    \"path\": \":categoryPath/page/:num/index.html\"\n}\n```\nNgoài các thuộc tính được giải thích trong hướng dẫn trước, EasyWeb còn có các thuộc tính mặc định\n\n```\nchildren: [],  // danh sách Danh Mục con (nếu có)\nparent: 'parent-category', //Tên của Danh Mục cha \nhref: 'url',   //link truy cập Danh Mục này\nfiles: [],     //chứa bài viết chi tiết thuộc danh mục\ncategory: '',   //tên của Danh Mục\n```\n\n> Với `AllCategory`, thuộc tính `parent` sẽ là null.\n\n#### Truy cập dữ liệu của Danh Mục\n> Tất cả Danh Mục của website được quản lý bởi Danh Mục gốc `AllCategory`, và sử dụng cú pháp HandleBar để truy cập \n\n* Sử dụng `lookupCategory` truy cập 1 Danh Mục.\nSau đây là 1 đoạn HTML code của trang Danh Mục\n```\n{{#with (lookupCategory AllCategory 'path-of-category') }}\n   <h1>Danh Muc <a href=\"#{{href}}\"{{metadata.name}}</a> </h1>\n   {{#each this.files}}\n     <li><a href=\"#{{this.path}}\"{{this.title}}</a></li>\n   {{/each}}\n{{/with}}\n```\n\nVới đoạn code mẫu trên, chúng ta có thể lấy dữ liệu `href` hoặc `metadata.name` của Danh Mục. Hoặc Lấy được danh sách bài viết chi tiết thuộc Danh Mục này trong thuộc tính `files` \n\n* Hoặc truy cập trực tiếp thuộc tính của Danh Mục nếu muốn\n```\n{{#each  (lookupCategory AllCategory 'path-of-category' 'files') }}\n\t<li><a href=\"#{{this.path}}\"{{this.title}}</a></li>\n{{/each}}\n```\n\n",
    "date": "12-09-2016 15:38:48"
}
---