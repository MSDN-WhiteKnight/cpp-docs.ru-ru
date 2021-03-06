---
title: /GR (Предоставление информации о типах во время выполнения)
ms.date: 11/04/2016
f1_keywords:
- /gr
- VC.Project.VCCLWCECompilerTool.RuntimeTypeInfo
- VC.Project.VCCLCompilerTool.RuntimeTypeInfo
helpviewer_keywords:
- -Gr compiler option [C++]
- Gr compiler option [C++]
- RTTI compiler option
- /Gr compiler option [C++]
- enable run-time type information compiler option [C++]
ms.assetid: d1f9f850-dcec-49fd-96ef-e72d01148906
ms.openlocfilehash: b0b618b1018912f1cf0172fc461ac2849c4faf5d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50579352"
---
# <a name="gr-enable-run-time-type-information"></a>/GR (Предоставление информации о типах во время выполнения)

Добавляет код для проверки типов объектов во время выполнения.

## <a name="syntax"></a>Синтаксис

```
/GR[-]
```

## <a name="remarks"></a>Примечания

Когда **/GR** имеет значение on, компилятор определяет `_CPPRTTI` макрос препроцессора. По умолчанию **/GR** включен. **Полиморфическом** отключает сведения о типе времени выполнения.

Используйте **/GR** если компилятору не удается разрешить тип объекта в коде статически. Как правило, требуется **/GR** при использовании в коде параметр [оператор dynamic_cast](../../cpp/dynamic-cast-operator.md) или [typeid](../../cpp/typeid-operator.md). Тем не менее **/GR** увеличивает размер разделов .rdata изображения. Если код использует **dynamic_cast** или **typeid**, **полиморфическом** может выдать изображение меньшего размера.

Дополнительные сведения о проверке типов во время выполнения, см. в разделе [сведения о типе времени выполнения](../../cpp/run-time-type-information.md) в *Справочник по языку C++*.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Нажмите кнопку **языка** страницу свойств.

1. Изменить **включить сведения о типе времени выполнения** свойство.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.RuntimeTypeInfo%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)