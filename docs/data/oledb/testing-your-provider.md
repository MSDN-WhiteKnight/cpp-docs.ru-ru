---
title: Тестирование поставщика
ms.date: 10/29/2018
helpviewer_keywords:
- testing, OLE DB providers
- testing providers
- OLE DB providers, testing
ms.assetid: bf824fe4-81af-4ffb-beb3-4fa2928dc450
ms.openlocfilehash: 9bb42af69a204c88e6068444642275b59ea5bf5c
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2018
ms.locfileid: "51518298"
---
# <a name="testing-your-provider"></a>Тестирование поставщика

Перед выпуском поставщика, необходимо выполнить следующие тесты в указанном порядке. Эти тесты показывают, что функции поставщика должным образом для большинства потенциальных пользователей.

1. Проверьте его поставщик с помощью [потребителя](../../data/oledb/creating-an-ole-db-consumer.md) приложение, написанное с помощью шаблонов потребителей OLE DB. Тестовый объект-получатель должен охватывать все функциональные области поставщика (все код, который был добавлен или изменен).

1. Проверьте его поставщик, используя приложение-потребитель, написанный с помощью ADO. Большинство разработчиков (особенно разработчиков Microsoft Visual Basic и Microsoft C#) использовать ADO или ADO.NET для клиентских приложений. Тестовый объект-получатель должен охватывать все функциональные области вашего поставщика. Пример приложения ADO потребителя, см. в разделе [примеры кода ADO в Microsoft Visual Basic](https://msdn.microsoft.com/library/ms807514.aspx).

1. Запустите проверка на совместимость OLE DB (включая проверка на совместимость с ADO), чтобы показать, что поставщик соответствует стандарту уровня 0 для поставщиков OLE DB. (Описание уровня 0, поиск **проверка на совместимость OLE DB уровня 0** в [Руководство программиста OLE DB](/sql/connect/oledb/ole-db/oledb-driver-for-sql-server-programming). Эти тесты и связанную документацию входят в состав Visual C++ в Data Access SDK. Эти тесты также помогают Показать, что ваш поставщик хорошо работает при сборке другими [поставщиками услуг](../../data/oledb/ole-db-resource-pooling-and-services.md) и особенно полезны при изменении или добавить свойства. Дополнительные сведения о проверка на совместимость см. в файле Readme для Data Access SDK, который находится на одном компакт-дисков Visual Studio.

## <a name="see-also"></a>См. также

[Работа с шаблонами поставщика OLE DB](../../data/oledb/working-with-ole-db-provider-templates.md)