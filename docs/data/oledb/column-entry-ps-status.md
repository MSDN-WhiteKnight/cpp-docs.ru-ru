---
title: "COLUMN_ENTRY_PS_STATUS | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: COLUMN_ENTRY_PS_STATUS
dev_langs: C++
helpviewer_keywords: COLUMN_ENTRY_PS_STATUS macro
ms.assetid: c02140c6-246f-4df5-8b86-698d7d137022
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a9066ca8439ddaa39f28eaef81f1d01f2fe5571a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="columnentrypsstatus"></a>COLUMN_ENTRY_PS_STATUS
Представляет привязку в наборе строк для конкретного столбца в базе данных.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
COLUMN_ENTRY_PS_STATUS(  
nOrdinal  
,   
nPrecision  
,   
nScale  
,   
data  
,   
status  
 )  
  
```  
  
#### <a name="parameters"></a>Параметры  
 В разделе [DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx) в *справочника программиста OLE DB*.  
  
 `nOrdinal`  
 [in] Номер столбца.  
  
 `nPrecision`  
 [in] Максимальная точность столбца, который требуется выполнить привязку.  
  
 `nScale`  
 [in] Масштаб столбца, необходимо выполнить привязку.  
  
 `data`  
 [in] Соответствующего члена данных в записи пользователя.  
  
 *status*  
 [in] Переменная может быть привязано к состояние столбца.  
  
## <a name="remarks"></a>Примечания  
 Можно указать точность и масштаб столбца, который требуется выполнить привязку. Этот макрос поддерживает *состояние* переменной. Он используется в следующих местах:  
  
-   Между [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md) и [END_COLUMN_MAP](../../data/oledb/end-column-map.md) макросы.  
  
-   Между [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md) и [END_ACCESSOR](../../data/oledb/end-accessor.md) макросы.  
  
-   Между [BEGIN_PARAM_MAP](../../data/oledb/begin-param-map.md) и [END_PARAM_MAP](../../data/oledb/end-param-map.md) макросы.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Макросы и глобальные функции для шаблонов потребителей OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)   
 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)   
 [COLUMN_ENTRY](../../data/oledb/column-entry.md)   
 [COLUMN_ENTRY_EX](../../data/oledb/column-entry-ex.md)   
 [COLUMN_ENTRY_LENGTH](../../data/oledb/column-entry-length.md)   
 [COLUMN_ENTRY_PS](../../data/oledb/column-entry-ps.md)   
 [COLUMN_ENTRY_PS_LENGTH](../../data/oledb/column-entry-ps-length.md)   
 [COLUMN_ENTRY_LENGTH_STATUS](../../data/oledb/column-entry-length-status.md)   
 [COLUMN_ENTRY_PS_LENGTH_STATUS](../../data/oledb/column-entry-ps-length-status.md)   
 [COLUMN_ENTRY_STATUS](../../data/oledb/column-entry-status.md)   
 [END_ACCESSOR](../../data/oledb/end-accessor.md)   
 [END_ACCESSOR_MAP](../../data/oledb/end-accessor-map.md)   
 [END_COLUMN_MAP](../../data/oledb/end-column-map.md)