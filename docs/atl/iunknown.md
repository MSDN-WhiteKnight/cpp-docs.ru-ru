---
title: IUnknown
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IUnknown
helpviewer_keywords:
- COM interfaces, base interface
- IUnknown interface
ms.assetid: e6b85472-e54b-4b8c-b19f-4454d6c05a8f
ms.openlocfilehash: 047e109e8098ed89ac89c05e434b54c91fda189a
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57270585"
---
# <a name="iunknown"></a>IUnknown

[IUnknown](/windows/desktop/api/unknwn/nn-unknwn-iunknown) является базовым интерфейсом каждого второго COM-интерфейса.  Этот интерфейс определяет три метода: [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)), [AddRef](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref), и [выпуска](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release). [QueryInterface](/windows/desktop/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)) позволяет пользователю интерфейса запрашивать указатель на другой интерфейс объекта. [AddRef](/windows/desktop/api/unknwn/nf-unknwn-iunknown-addref) и [выпуска](/windows/desktop/api/unknwn/nf-unknwn-iunknown-release) реализуют подсчет ссылок в интерфейсе.

## <a name="see-also"></a>См. также

[Введение в модель COM](../atl/introduction-to-com.md)<br/>
[IUnknown и наследование интерфейса](/windows/desktop/com/iunknown-and-interface-inheritance)
