---
title: Добавление интерфейса в поставщик
ms.date: 10/29/2018
helpviewer_keywords:
- OLE DB provider templates, object interfaces
ms.assetid: b0fc7cf8-428a-4584-9d64-ce9074d0eb66
ms.openlocfilehash: 5659078641439744c1f68cbb399c19b9b58bd0bb
ms.sourcegitcommit: 943c792fdabf01c98c31465f23949a829eab9aad
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2018
ms.locfileid: "51265143"
---
# <a name="adding-an-interface-to-your-provider"></a>Добавление интерфейса в поставщик

Определить, каким объектам требуется добавить интерфейс (обычно созданные объекты данных источника, набор строк, команды или сеанса **мастер поставщика OLE DB**). Вполне возможно, что объект, необходимо добавить интерфейс — это приложения, в настоящее время не поддерживает поставщик. В этом случае запустите **мастер поставщика ATL OLE DB** для создания объекта. Щелкните правой кнопкой мыши проект в **представление классов**, нажмите кнопку **добавить** > **новый элемент** меню, выберите **установленные**  >  **Visual C++** > **ATL**, а затем нажмите кнопку **поставщик OLEDB библиотеки ATL**. Может потребоваться разместить код интерфейса в отдельном каталоге, а затем скопируйте файлы в проект поставщика.

Если вы создали новый класс для поддержки интерфейса, следует наследовать от этого класса объект. Например, можно добавить класс `IRowsetIndexImpl` для объекта набора строк:

```cpp
template <class Creator>
class CCustomRowset :
    public CRowsetImpl< CCustomRowset<Creator>, CCustomWindowsFile, Creator>,
    public IRowsetIndexImpl< ... >
```

Добавьте интерфейс в объекте с помощью макроса COM_INTERFACE_ENTRY COM_MAP. Если файл сопоставления отсутствует, создайте его. Пример:

```cpp
BEGIN_COM_MAP(CCustomRowset)
     COM_INTERFACE_ENTRY(IRowsetIndex)
END_COM_MAP()
```

Объект набора строк цепочка карты родительского объекта таким образом, объект можно делегировать в родительский класс. В этом примере добавьте макрос COM_INTERFACE_ENTRY_CHAIN карты:

```cpp
BEGIN_COM_MAP(CCustomRowset)
     COM_INTERFACE_ENTRY(IRowsetIndex)
     COM_INTERFACE_ENTRY_CHAIN(CRowsetImpl)
END_COM_MAP()
```

## <a name="see-also"></a>См. также

[Работа с шаблонами поставщика OLE DB](../../data/oledb/working-with-ole-db-provider-templates.md)