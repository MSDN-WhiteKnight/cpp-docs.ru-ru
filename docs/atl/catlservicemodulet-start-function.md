---
title: Функция CAtlServiceModuleT::Start
ms.date: 11/04/2016
f1_keywords:
- CServiceModule.Start
- CServiceModule::Start
helpviewer_keywords:
- Start method
ms.assetid: b5193a23-41bc-42d2-8d55-3eb43dc62238
ms.openlocfilehash: 806cd8ec353e2111d249472fb9aa885e7548baab
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57265162"
---
# <a name="catlservicemoduletstart-function"></a>Функция CAtlServiceModuleT::Start

При запуске службы `_tWinMain` вызовы `CAtlServiceModuleT::WinMain`, который в свою очередь вызывает `CAtlServiceModuleT::Start`.

`CAtlServiceModuleT::Start` Задает массив `SERVICE_TABLE_ENTRY` структур, которые сопоставляются его функция запуска каждой службы. Этот массив передается в функцию Win32 API, [StartServiceCtrlDispatcher](/windows/desktop/api/winsvc/nf-winsvc-startservicectrldispatchera). В теории, один исполняемый ФАЙЛ может обрабатывать несколько служб, и массив может иметь несколько `SERVICE_TABLE_ENTRY` структуры. Тем не менее, в настоящее время это служба, созданный ATL поддерживает только одну службу в EXE-файла. Таким образом, массив содержит единственную запись, которая содержит имя службы и `_ServiceMain` как функцию запуска. `_ServiceMain` — Это статическая функция-член из `CAtlServiceModuleT` , вызывает функцию-член, `ServiceMain`.

> [!NOTE]
>  Сбой `StartServiceCtrlDispatcher` для подключения к службе управления manager (SCM), скорее всего, означает, что программа не выполняется как служба. В этом случае программа вызывает `CAtlServiceModuleT::Run` напрямую, чтобы программа может запускаться как локальный сервер. Дополнительные сведения о запуске программы как локального сервера, см. в разделе [упрощению](../atl/debugging-tips.md).

## <a name="see-also"></a>См. также

[Службы](../atl/atl-services.md)<br/>
[CAtlServiceModuleT::Start](../atl/reference/catlservicemodulet-class.md#start)
