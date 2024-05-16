### ロジスティクス管理システム

#### 1. 在庫管理画面

```
--------------------------------------------------------------
| Inventory Management                                      |
|------------------------------------------------------------|
| [Menu]                          | [Content]                |
|------------------------------------------------------------|
| [Add New Item]                  | Inventory List           |
| - Inventory List                | ----------------------------------------- |
| - Display Management            | | ID  | Name    | Category | Quantity | Updated Date | |
| - Database Management           | |-----|---------|----------|----------|--------------| |
| - Notifications & Integration   | | 1001| Item1   | Cat1     | 100      | 2023-05-01   | |
|                                 | | 1002| Item2   | Cat2     | 50       | 2023-05-02   | |
|                                 | ----------------------------------------- |
|                                 | [Edit] [Delete]                           |
|------------------------------------------------------------|
| Item Details                                                |
| ---------------------------------------------------------- |
| ID: [_____]                                                 |
| Name: [_____________________]                               |
| Category: [_____________________]                           |
| Quantity: [_____]                                           |
| Location: [_____________________]                           |
| Status: [_____________________]                             |
| Image URL: [_____________________]                          |
| Registration Date: [_____________________]                  |
| Update Date: [_____________________]                        |
| Manufacture Date: [_____________________]                   |
| Registered By: [_____________________]                      |
| Updated By: [_____________________]                         |
| [Save] [Cancel]                                             |
--------------------------------------------------------------
```

#### 2. 通知・連携画面

```
--------------------------------------------------------------
| Notifications & Integration                               |
|------------------------------------------------------------|
| [Menu]                          | [Content]                |
|------------------------------------------------------------|
| [Add New Notification]           | Notification List       |
| - Inventory List                | -------------------------------------------------- |
| - Display Management            | | ID  | Type     | Status  | Date       | Registered By | |
| - Database Management           | |-----|----------|---------|------------|--------------| |
| - Notifications & Integration   | | 2001| New Item | Read    | 2023-05-01 | User1        | |
|                                 | | 2002| Low Stock| Unread  | 2023-05-02 | User2        | |
|                                 | -------------------------------------------------- |
|                                 | [Edit] [Delete]                   |
|------------------------------------------------------------|
| Notification Details                                        |
| ---------------------------------------------------------- |
| ID: [_____]                                                 |
| Type: [_____________________]                               |
| Status: [_____________________]                             |
| Date: [_____________________]                               |
| Registered By: [_____________________]                      |
| Intent: [_____________________]                             |
| Details: [_____________________]                            |
| [Save] [Cancel]                                             |
--------------------------------------------------------------
```

### データベース設計

#### テーブル一覧

1. **Inventory**: 在庫情報を管理
2. **Notifications**: 通知情報を管理

#### データベーススキーマ

```sql
-- 在庫情報
CREATE TABLE Inventory (
    InventoryID INT PRIMARY KEY,
    Name VARCHAR(255),
    Category VARCHAR(255),
    Quantity INT,
    Location VARCHAR(255),
    Status VARCHAR(255),
    ImageURL VARCHAR(255),
    RegistrationDate TIMESTAMP,
    UpdateDate TIMESTAMP,
    ManufactureDate TIMESTAMP,
    RegisteredBy VARCHAR(255),
    UpdatedBy VARCHAR(255)
);

-- 通知情報
CREATE TABLE Notifications (
    NotificationID INT PRIMARY KEY,
    Type VARCHAR(255),
    Status VARCHAR(255),
    Date TIMESTAMP,
    RegisteredBy VARCHAR(255),
    Intent TEXT,
    Details TEXT
);
