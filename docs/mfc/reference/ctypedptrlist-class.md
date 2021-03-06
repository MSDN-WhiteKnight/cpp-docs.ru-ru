---
title: CTypedPtrList Class
ms.date: 11/04/2016
f1_keywords:
- CTypedPtrList
- AFXTEMPL/CTypedPtrList
- AFXTEMPL/CTypedPtrList::AddHead
- AFXTEMPL/CTypedPtrList::AddTail
- AFXTEMPL/CTypedPtrList::GetAt
- AFXTEMPL/CTypedPtrList::GetHead
- AFXTEMPL/CTypedPtrList::GetNext
- AFXTEMPL/CTypedPtrList::GetPrev
- AFXTEMPL/CTypedPtrList::GetTail
- AFXTEMPL/CTypedPtrList::RemoveHead
- AFXTEMPL/CTypedPtrList::RemoveTail
- AFXTEMPL/CTypedPtrList::SetAt
helpviewer_keywords:
- CTypedPtrList [MFC], AddHead
- CTypedPtrList [MFC], AddTail
- CTypedPtrList [MFC], GetAt
- CTypedPtrList [MFC], GetHead
- CTypedPtrList [MFC], GetNext
- CTypedPtrList [MFC], GetPrev
- CTypedPtrList [MFC], GetTail
- CTypedPtrList [MFC], RemoveHead
- CTypedPtrList [MFC], RemoveTail
- CTypedPtrList [MFC], SetAt
ms.assetid: c273096e-1756-4340-864b-4a08b674a65e
ms.openlocfilehash: 756ef5043468f614c6ab3ac64598d62b29b2dc41
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57286027"
---
# <a name="ctypedptrlist-class"></a>CTypedPtrList Class

Предоставляет типобезопасную "программу-оболочку" для объектов класса `CPtrList`.

## <a name="syntax"></a>Синтаксис

```
template<class BASE_CLASS, class TYPE>
class CTypedPtrList : public BASE_CLASS
```

#### <a name="parameters"></a>Параметры

*BASE_CLASS*<br/>
Базовый класс для класса типизированных указателей списка; должен быть классом списка указатель ( `CObList` или `CPtrList`).

*ТИП*<br/>
Тип элементов, содержащихся в списке базовых классов.

## <a name="members"></a>Участники

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CTypedPtrList::AddHead](#addhead)|Добавляет элемент (или все элементы из другого списка) в начало списка (делает нового заголовка).|
|[CTypedPtrList::AddTail](#addtail)|Добавляет в конец списка (делает новый tail) элемента (или все элементы из другого списка).|
|[CTypedPtrList::GetAt](#getat)|Получает элемент в заданной позиции.|
|[CTypedPtrList::GetHead](#gethead)|Возвращает головной элемент списка (не может быть пустым).|
|[CTypedPtrList::GetNext](#getnext)|Получает следующий элемент для выполнения итерации.|
|[CTypedPtrList::GetPrev](#getprev)|Возвращает предыдущий элемент для выполнения итерации.|
|[CTypedPtrList::GetTail](#gettail)|Возвращает заключительный фрагмент элемент списка (не может быть пустым).|
|[CTypedPtrList::RemoveHead](#removehead)|Удаляет элемент из головы списка.|
|[CTypedPtrList::RemoveTail](#removetail)|Удаляет элемент из конца списка.|
|[CTypedPtrList::SetAt](#setat)|Задает элемент в заданной позиции.|

## <a name="remarks"></a>Примечания

При использовании `CTypedPtrList` вместо `CObList` или `CPtrList`, средство проверки типов C++ помогает устранить ошибки, вызванные типы несоответствие указателей.

Кроме того `CTypedPtrList` оболочки выполняет большей части приведения, которое будет обязательным, если вы использовали `CObList` или `CPtrList`.

Так как все `CTypedPtrList` функции, встроенные, использование этого шаблона незначительно повлиять на размер или скорость кода.

Списки производным от `CObList` могут быть сериализованы, но типы, производные от `CPtrList` невозможно.

Когда `CTypedPtrList` объект удаляется или когда его элементы удаляются, удаляются только указатели, не сущностями, которые они ссылаются.

Дополнительные сведения об использовании `CTypedPtrList`, см. в статьях [коллекций](../../mfc/collections.md) и [классы на основе шаблона](../../mfc/template-based-classes.md).

## <a name="example"></a>Пример

В этом примере создается экземпляр `CTypedPtrList`, добавляет один объект, сериализует списка на диск и затем удаляет объект:

[!code-cpp[NVC_MFCCollections#110](../../mfc/codesnippet/cpp/ctypedptrlist-class_1.cpp)]

[!code-cpp[NVC_MFCCollections#111](../../mfc/codesnippet/cpp/ctypedptrlist-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`BASE_CLASS`

`_CTypedPtrList`

`CTypedPtrList`

## <a name="requirements"></a>Требования

**Заголовок:** afxtempl.h

##  <a name="addhead"></a>  CTypedPtrList::AddHead

Эта функция-член вызывает `BASE_CLASS` **:: AddHead**.

```
POSITION AddHead(TYPE newElement);
void AddHead(CTypedPtrList<BASE_CLASS, TYPE>* pNewList);
```

### <a name="parameters"></a>Параметры

*ТИП*<br/>
Тип элементов, содержащихся в списке базовых классов.

*newElement*<br/>
Указатель на объект, добавляемый в этот список. Допускается значение NULL.

*BASE_CLASS*<br/>
Базовый класс для класса типизированных указателей списка; должен быть классом списка указатель ( [CObList](../../mfc/reference/coblist-class.md) или [CPtrList](../../mfc/reference/cptrlist-class.md)).

*pNewList*<br/>
Указатель на другую [CTypedPtrList](../../mfc/reference/ctypedptrlist-class.md) объекта. Элементы в *pNewList* будут добавляться в этот список.

### <a name="return-value"></a>Возвращаемое значение

Первая версия возвращает значение ПОЗИЦИИ вставленный элемент.

### <a name="remarks"></a>Примечания

Первая версия добавляет новый элемент перед заголовок списка. Вторая версия добавляет другой список элементов, прежде чем заголовок.

##  <a name="addtail"></a>  CTypedPtrList::AddTail

Эта функция-член вызывает `BASE_CLASS` **:: AddTail**.

```
POSITION AddTail(TYPE newElement);
void AddTail(CTypedPtrList<BASE_CLASS, TYPE>* pNewList);
```

### <a name="parameters"></a>Параметры

*ТИП*<br/>
Тип элементов, содержащихся в списке базовых классов.

*newElement*<br/>
Указатель на объект, добавляемый в этот список. Допускается значение NULL.

*BASE_CLASS*<br/>
Базовый класс для класса типизированных указателей списка; должен быть классом списка указатель ( [CObList](../../mfc/reference/coblist-class.md) или [CPtrList](../../mfc/reference/cptrlist-class.md)).

*pNewList*<br/>
Указатель на другую [CTypedPtrList](../../mfc/reference/ctypedptrlist-class.md) объекта. Элементы в *pNewList* будут добавляться в этот список.

### <a name="return-value"></a>Возвращаемое значение

Первая версия возвращает значение ПОЗИЦИИ вставленный элемент.

### <a name="remarks"></a>Примечания

Первая версия добавляет новый элемент после конца списка. Вторая версия добавляет другой список элементов после конца списка.

##  <a name="getat"></a>  CTypedPtrList::GetAt

Переменная типа ПОЗИЦИЯ — это ключ для списка.

```
TYPE& GetAt(POSITION position);
TYPE GetAt(POSITION position) const;
```

### <a name="parameters"></a>Параметры

*ТИП*<br/>
Параметр шаблона, указывающий тип элементов, хранящихся в списке.

*положение*<br/>
Значение ПОЗИЦИИ, возвращенное предыдущим `GetHeadPosition` или `Find` вызова функции-члена.

### <a name="return-value"></a>Возвращаемое значение

Если список осуществляется через указатель на `const CTypedPtrList`, затем `GetAt` возвращает указатель типа, указанного в параметре шаблона *тип*. Это позволяет использовать только в правой части оператора присваивания функции и тем самым защищает списка от изменения.

Если список осуществляется напрямую или через указатель в `CTypedPtrList`, затем `GetAt` возвращает ссылку на указатель типа, указанного в параметре шаблона *тип*. Это позволяет функции для использования с обеих сторон оператора присваивания и таким образом позволяет изменять записи в списке.

### <a name="remarks"></a>Примечания

Это не так же, как индекс, и вы не можете работать значение ПОЗИЦИИ самостоятельно. `GetAt` Извлекает `CObject` указатель, связанный с заданной позиции.

Необходимо убедиться, что значение в ПОЗИЦИИ представляет допустимую позицию в списке. Если он является недопустимым, утверждает отладочную версию библиотеки Microsoft Foundation Class.

Это встраиваемая функция вызывает `BASE_CLASS` **:: GetAt**.

##  <a name="gethead"></a>  CTypedPtrList::GetHead

Получает указатель, который представляет головной элемент этого списка.

```
TYPE& GetHead();
TYPE GetHead() const;
```

### <a name="parameters"></a>Параметры

*ТИП*<br/>
Параметр шаблона, указывающий тип элементов, хранящихся в списке.

### <a name="return-value"></a>Возвращаемое значение

Если список осуществляется через указатель на `const CTypedPtrList`, затем `GetHead` возвращает указатель типа, указанного в параметре шаблона *тип*. Это позволяет использовать только в правой части оператора присваивания функции и тем самым защищает списка от изменения.

Если список осуществляется напрямую или через указатель в `CTypedPtrList`, затем `GetHead` возвращает ссылку на указатель типа, указанного в параметре шаблона *тип*. Это позволяет функции для использования с обеих сторон оператора присваивания и таким образом позволяет изменять записи в списке.

### <a name="remarks"></a>Примечания

Необходимо убедиться, что список не является пустым, перед вызовом `GetHead`. Если список пуст, утверждает отладочную версию библиотеки Microsoft Foundation Class. Используйте [IsEmpty](../../mfc/reference/coblist-class.md#isempty) чтобы убедиться, что список содержит элементы.

##  <a name="getnext"></a>  CTypedPtrList::GetNext

Получает элемент списка, идентифицируемый *rPosition*, затем задает *rPosition* значению ПОЗИЦИИ на следующую запись в списке.

```
TYPE& GetNext(POSITION& rPosition);
TYPE GetNext(POSITION& rPosition) const;
```

### <a name="parameters"></a>Параметры

*ТИП*<br/>
Параметр шаблона, указывающий тип элементов, содержащихся в данном списке.

*rPosition*<br/>
Ссылку на значение ПОЗИЦИИ, возвращенное предыдущим `GetNext`, `GetHeadPosition`, или другим вызовом функции-члена.

### <a name="return-value"></a>Возвращаемое значение

Если список осуществляется через указатель на `const CTypedPtrList`, затем `GetNext` возвращает указатель типа, указанного в параметре шаблона *тип*. Это позволяет использовать только в правой части оператора присваивания функции и тем самым защищает списка от изменения.

Если список осуществляется напрямую или через указатель в `CTypedPtrList`, затем `GetNext` возвращает ссылку на указатель типа, указанного в параметре шаблона *тип*. Это позволяет функции для использования с обеих сторон оператора присваивания и таким образом позволяет изменять записи в списке.

### <a name="remarks"></a>Примечания

Можно использовать `GetNext` в цикле прямой итерации, если установить начальное положение, с помощью вызова `GetHeadPosition` или [CPtrList::Find](../../mfc/reference/coblist-class.md#find).

Необходимо убедиться, что значение в ПОЗИЦИИ представляет допустимую позицию в списке. Если он является недопустимым, утверждает отладочную версию библиотеки Microsoft Foundation Class.

Если полученного элемента является последним в списке, то новое значение *rPosition* имеет значение NULL.

Существует возможность удалить элемент во время итерации. См. в примере [CObList::RemoveAt](../../mfc/reference/coblist-class.md#removeat).

##  <a name="getprev"></a>  CTypedPtrList::GetPrev

Получает элемент списка, идентифицируемый *rPosition*, затем задает *rPosition* значению положение предыдущего элемента в списке.

```
TYPE& GetPrev(POSITION& rPosition);
TYPE GetPrev(POSITION& rPosition) const;
```

### <a name="parameters"></a>Параметры

*ТИП*<br/>
Параметр шаблона, указывающий тип элементов, содержащихся в данном списке.

*rPosition*<br/>
Ссылку на значение ПОЗИЦИИ, возвращенное предыдущим `GetPrev` или другим вызовом функции-члена.

### <a name="return-value"></a>Возвращаемое значение

Если список осуществляется через указатель на `const CTypedPtrList`, затем `GetPrev` возвращает указатель типа, указанного в параметре шаблона *тип*. Это позволяет использовать только в правой части оператора присваивания функции и тем самым защищает списка от изменения.

Если список осуществляется напрямую или через указатель в `CTypedPtrList`, затем `GetPrev` возвращает ссылку на указатель типа, указанного в параметре шаблона *тип*. Это позволяет функции для использования с обеих сторон оператора присваивания и таким образом позволяет изменять записи в списке.

### <a name="remarks"></a>Примечания

Можно использовать `GetPrev` в цикле обратной итерации, если установить начальное положение, с помощью вызова `GetTailPosition` или `Find`.

Необходимо убедиться, что значение в ПОЗИЦИИ представляет допустимую позицию в списке. Если он является недопустимым, утверждает отладочную версию библиотеки Microsoft Foundation Class.

Если полученного элемента является первым в списке, выберите новое значение *rPosition* имеет значение NULL.

##  <a name="gettail"></a>  CTypedPtrList::GetTail

Получает указатель, который представляет головной элемент этого списка.

```
TYPE& GetTail();
TYPE GetTail() const;
```

### <a name="parameters"></a>Параметры

*ТИП*<br/>
Параметр шаблона, указывающий тип элементов, хранящихся в списке.

### <a name="return-value"></a>Возвращаемое значение

Если список осуществляется через указатель на `const CTypedPtrList`, затем `GetTail` возвращает указатель типа, указанного в параметре шаблона *тип*. Это позволяет использовать только в правой части оператора присваивания функции и тем самым защищает списка от изменения.

Если список осуществляется напрямую или через указатель в `CTypedPtrList`, затем `GetTail` возвращает ссылку на указатель типа, указанного в параметре шаблона *тип*. Это позволяет функции для использования с обеих сторон оператора присваивания и таким образом позволяет изменять записи в списке.

### <a name="remarks"></a>Примечания

Необходимо убедиться, что список не является пустым, перед вызовом `GetTail`. Если список пуст, утверждает отладочную версию библиотеки Microsoft Foundation Class. Используйте [IsEmpty](../../mfc/reference/coblist-class.md#isempty) чтобы убедиться, что список содержит элементы.

##  <a name="removehead"></a>  CTypedPtrList::RemoveHead

Удаляет элемент из головы списка и возвращает его.

```
TYPE RemoveHead();
```

### <a name="parameters"></a>Параметры

*ТИП*<br/>
Параметр шаблона, указывающий тип элементов, хранящихся в списке.

### <a name="return-value"></a>Возвращаемое значение

Указатель, который ранее в начало списка. Указатель относится к типу, указанному в параметре шаблона *тип*.

### <a name="remarks"></a>Примечания

Необходимо убедиться, что список не является пустым, перед вызовом `RemoveHead`. Если список пуст, утверждает отладочную версию библиотеки Microsoft Foundation Class. Используйте [IsEmpty](../../mfc/reference/coblist-class.md#isempty) чтобы убедиться, что список содержит элементы.

##  <a name="removetail"></a>  CTypedPtrList::RemoveTail

Удаляет элемент из конца списка и возвращает его.

```
TYPE RemoveTail();
```

### <a name="parameters"></a>Параметры

*ТИП*<br/>
Параметр шаблона, указывающий тип элементов, хранящихся в списке.

### <a name="return-value"></a>Возвращаемое значение

Указатель, который ранее в конец списка. Указатель относится к типу, указанному в параметре шаблона *тип*.

### <a name="remarks"></a>Примечания

Необходимо убедиться, что список не является пустым, перед вызовом `RemoveTail`. Если список пуст, утверждает отладочную версию библиотеки Microsoft Foundation Class. Используйте [IsEmpty](../../mfc/reference/coblist-class.md#isempty) чтобы убедиться, что список содержит элементы.

##  <a name="setat"></a>  CTypedPtrList::SetAt

Эта функция-член вызывает `BASE_CLASS` **:: SetAt**.

```
void SetAt(POSITION pos, TYPE newElement);
```

### <a name="parameters"></a>Параметры

*торговых терминалов*<br/>
ПОЗИЦИЯ элемента, который требуется задать.

*ТИП*<br/>
Тип элементов, содержащихся в списке базовых классов.

*newElement*<br/>
Указатель на объект для записи в список.

### <a name="remarks"></a>Примечания

Переменная типа ПОЗИЦИЯ — это ключ для списка. Это не так же, как индекс, и вы не можете работать значение ПОЗИЦИИ самостоятельно. `SetAt` Записывает указатель на объект в указанной позиции в списке.

Необходимо убедиться, что значение в ПОЗИЦИИ представляет допустимую позицию в списке. Если он является недопустимым, утверждает отладочную версию библиотеки Microsoft Foundation Class.

Дополнительные примечания, см. в разделе [CObList::SetAt](../../mfc/reference/coblist-class.md#setat).

## <a name="see-also"></a>См. также

[Пример MFC СБОР](../../visual-cpp-samples.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CPtrList](../../mfc/reference/cptrlist-class.md)<br/>
[Класс CObList](../../mfc/reference/coblist-class.md)
