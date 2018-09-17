---
title: -GR (предоставление информации типа времени выполнения) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /gr
- VC.Project.VCCLWCECompilerTool.RuntimeTypeInfo
- VC.Project.VCCLCompilerTool.RuntimeTypeInfo
dev_langs:
- C++
helpviewer_keywords:
- -Gr compiler option [C++]
- Gr compiler option [C++]
- RTTI compiler option
- /Gr compiler option [C++]
- enable run-time type information compiler option [C++]
ms.assetid: d1f9f850-dcec-49fd-96ef-e72d01148906
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 24ef844c716d64e609440d41bf55db20308c02f1
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45712248"
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