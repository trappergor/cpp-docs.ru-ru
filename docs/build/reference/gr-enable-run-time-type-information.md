---
title: /GR (Предоставление информации о типах во время выполнения)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLWCECompilerTool.RuntimeTypeInfo
- VC.Project.VCCLCompilerTool.RuntimeTypeInfo
helpviewer_keywords:
- -Gr compiler option [C++]
- Gr compiler option [C++]
- RTTI compiler option
- /Gr compiler option [C++]
- enable run-time type information compiler option [C++]
ms.assetid: d1f9f850-dcec-49fd-96ef-e72d01148906
ms.openlocfilehash: ee1398b2f9ee78c62fb84aa591e77708cd0d9d83
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79439597"
---
# <a name="gr-enable-run-time-type-information"></a>/GR (Предоставление информации о типах во время выполнения)

Добавляет код для проверки типов объектов во время выполнения.

## <a name="syntax"></a>Синтаксис

```
/GR[-]
```

## <a name="remarks"></a>Remarks

Если параметр **/GR** имеет значение ON, компилятор определяет `_CPPRTTI` макрос препроцессора. По умолчанию **/GR** имеет значение ON. **/GR-** отключает сведения о типах времени выполнения.

Используйте **/GR** , если компилятор не может статически разрешить тип объекта в коде. Обычно требуется параметр **/GR** , если в коде используется [оператор dynamic_cast](../../cpp/dynamic-cast-operator.md) или [typeid](../../cpp/typeid-operator.md). Однако **/GR** увеличивает размер разделов RDATA изображения. Если в коде не используется **dynamic_cast** или **typeid**, **/GR-** может создать меньшее изображение.

Дополнительные сведения о проверке типов во время выполнения см. в разделе [сведения о типах во время выполнения](../../cpp/run-time-type-information.md) в  *C++ справочнике по языку*.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Подробнее см. в статье [Настройка компилятора C++ и свойства сборки в Visual Studio](../working-with-project-properties.md).

1. Откройте папку **C/C++** .

1. Перейдите на страницу свойств **язык** .

1. Измените свойство **включить сведения о типе времени выполнения** .

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.RuntimeTypeInfo%2A>.

## <a name="see-also"></a>См. также раздел

[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)
