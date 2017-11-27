---
title: "-showIncludes (список содержит файлы) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCCLWCECompilerTool.ShowIncludes
- VC.Project.VCCLCompilerTool.ShowIncludes
- /showincludes
dev_langs: C++
helpviewer_keywords:
- include files
- /showIncludes compiler option [C++]
- include files, displaying in compilation
- -showIncludes compiler option [C++]
- showIncludes compiler option [C++]
ms.assetid: 0b74b052-f594-45a6-a7c7-09e1a319547d
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 72f80202d2d1c8018e9c145951664d335ac759b7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="showincludes-list-include-files"></a>/showIncludes (список включаемых файлов)
Компилятор выводит список включаемых файлов. Вложенные включают файлы также являются отображаемые (файлы, включенные файлы, которые включены).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/showIncludes  
```  
  
## <a name="remarks"></a>Примечания  
 Когда компилятор встречает включаемый файл, выводится сообщение, например:  
  
```  
Note: including file: d:\MyDir\include\stdio.h  
```  
  
 Вложенные включают файлы отмечаются отступом, один пробел для каждого уровня вложенности, например:  
  
```  
Note: including file: d:\temp\1.h  
Note: including file:  d:\temp\2.h  
```  
  
 В этом случае `2.h` был включен в `1.h`, поэтому отступы.  
  
 **/Showincludes** передает параметр в `stderr`, а не `stdout`.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Откройте папку **C/C++** .  
  
3.  Нажмите кнопку **Дополнительно** страницу свойств.  
  
4.  Изменить **Показать включает** свойство.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ShowIncludes%2A>.  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)