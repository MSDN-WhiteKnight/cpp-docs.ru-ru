---
title: Предупреждение компилятора (уровень 1) C4819
ms.date: 11/04/2016
f1_keywords:
- C4819
helpviewer_keywords:
- C4819
ms.assetid: c0316e85-249c-414d-9df0-622d077c6bc2
ms.openlocfilehash: c0ca29a304fbd05cb0c6b7d1b06414304c70fb2a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50596616"
---
# <a name="compiler-warning-level-1-c4819"></a>Предупреждение компилятора (уровень 1) C4819

Файл содержит символ, который нельзя отобразить с помощью текущей кодовой страницы (номер). Сохраните файл в формате Юникода, чтобы избежать потери данных.

Ошибка C4819 возникает, когда файл исходного кода ANSI компилируется в системе, кодовая страница которой не может отобразить все символы файла.

Чтобы устранить ошибку C4819, сохраните файл в формате Юникода. В Visual Studio, выберите **файл**, **Дополнительные параметры сохранения**. В **Дополнительные параметры сохранения** диалогового окна выберите кодировку, способную отобразить все символы в файле — например, UTF-8 и нажмите кнопку **ОК**.