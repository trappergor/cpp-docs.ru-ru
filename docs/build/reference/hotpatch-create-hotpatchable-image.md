---
title: /hotpatch (Создать образ с обновлениями)
ms.date: 11/12/2018
f1_keywords:
- /hotpatch
- VC.Project.VCCLCompilerTool.CreateHotpatchableImage
helpviewer_keywords:
- hot patching
- -hotpatch compiler option [C++]
- /hotpatch compiler option [C++]
- hotpatching
ms.assetid: aad539b6-c053-4c78-8682-853d98327798
ms.openlocfilehash: 8830b26b8fdfc3db2aa5fe31a52e6226fd554946
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62291656"
---
# <a name="hotpatch-create-hotpatchable-image"></a>/hotpatch (Создать образ с обновлениями)

Готовит образ к оперативному исправлению.

## <a name="syntax"></a>Синтаксис

```
/hotpatch
```

## <a name="remarks"></a>Примечания

Когда **/hotpatch** используется в процессе компиляции компилятор гарантирует, что первой инструкции каждой функции по крайней мере два байта, который необходим для критического обновления.

Чтобы завершить подготовку для создания образа с обновлением, после использования **/hotpatch** для компиляции, необходимо использовать [/FUNCTIONPADMIN (создать образ с обновлениями)](functionpadmin-create-hotpatchable-image.md) для связывания. Компиляция и связывание изображения с помощью одного вызова cl.exe, **/hotpatch** подразумевает **/functionpadmin**.

Так как инструкции всегда по два байта или больше для архитектуры ARM и поскольку x64 компиляции всегда рассматривается так, как если **/hotpatch** была определена, нет необходимости указывать **/hotpatch** при Компиляция для этих целевых объектов; Тем не менее, по-прежнему необходимо связать с помощью **/functionpadmin** для создания образов с обновлениями для них. **/Hotpatch** компиляции x86 влияет на единственный параметр компилятора.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Выберите **C/C++** папки.

1. Выберите **командной строки** страницу свойств.

1. Добавить параметр компилятора для **Дополнительные параметры** поле.

### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора MSVC](compiler-options.md)<br/>
[Синтаксис командной строки компилятора MSVC](compiler-command-line-syntax.md)
