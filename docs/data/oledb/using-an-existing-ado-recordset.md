---
title: Использование существующего набора записей ADO
ms.date: 11/04/2016
helpviewer_keywords:
- ADO recordsets [C++]
- OLE DB consumer templates, ADO recordsets
- recordsets [C++], using in OLE DB
ms.assetid: a9b1de8a-d379-49b1-a26e-578741e9f6a8
ms.openlocfilehash: 62e56b818a766bf3b7efddf9243ffd47ad2cb46f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50610604"
---
# <a name="using-an-existing-ado-recordset"></a>Использование существующего набора записей ADO

Создайте шаблоны потребителей OLE DB и Active Data Objects (ADO), открыть набор записей (соответствующий набор строк в шаблоны потребителей OLE DB) с помощью ADO. Если у вас есть набор записей, выполните следующие действия для подключения к набор строк OLE DB.

1. Вызовите `QueryInterface` для `IRowset` и `IAccessor` указатели.

    ```cpp
    IRowset* lpRowset = NULL;
    IAccessor* lpAccessor = NULL;
    lpUnk->QueryInterface(IID_IRowset, (void**)&lpRowset);
    lpUnk->QueryInterface(IID_IAccessor, (void**)&lpAccessor);
    ```

    > [!NOTE]
    > *lpUnk* указывает `IUnknown` объекта набора записей ADO.

1. Назначить их соответствующие классы шаблонов потребителей OLE DB для доступа и строк.

    ```cpp
    CRowset rs;
    CAccessor accessor;

    accessor.AddAccessorInfo(0ul);      // 0 is the ordinal of an ADO accessor
    rs.m_spRowset.Attach(lpRowset);      // use the Attach method of CComPtr<>
    rs.SetAccessor(accessor);
    ```

## <a name="see-also"></a>См. также

[Использование методов доступа](../../data/oledb/using-accessors.md)