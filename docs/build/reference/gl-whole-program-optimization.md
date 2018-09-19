---
title: -GL (оптимизация всей программы) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /gl
- VC.Project.VCCLWCECompilerTool.WholeProgramOptimization
dev_langs:
- C++
helpviewer_keywords:
- /GL compiler option [C++]
- whole program optimizations and C++ compiler
- -GL compiler option [C++]
- GL compiler option [C++]
ms.assetid: 09d51e2d-9728-4bd0-b5dc-3b8284aca1d1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 97561a63a21550cc06f29a95f6ddf05687758b83
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45723662"
---
# <a name="gl-whole-program-optimization"></a>/GL (оптимизация всей программы)

Включает оптимизацию всей программы.

## <a name="syntax"></a>Синтаксис

```
/GL[-]
```

## <a name="remarks"></a>Примечания

Оптимизация всей программы позволяет компилятору выполнить оптимизацию с помощью информации о всех модулях в программе. Без оптимизации всей программы, оптимизация выполняется на основе модуля (объекта компиляции).

Оптимизация всей программы по умолчанию и должен быть явным образом включен. Тем не менее, можно также явным образом отключить с помощью **/GL-**.

Сведения о всех модулей компилятор выполнять следующие действия.

- Оптимизируйте использование регистров за границами функций.

- Улучшенным отслеживать изменения глобальных данных, что позволит уменьшить количество загрузки и сохранения.

- Улучшенным отслеживания разыменования возможный набор элементов, измененных с помощью указателя, уменьшая число загрузок и хранилищ.

- Встроенные функции в модуле даже в том случае, если функция определена в другом модуле.

OBJ-файлы, формируемой с помощью **/GL** будут недоступны для таких программ компоновщика, как [EDITBIN](../../build/reference/editbin-reference.md) и [DUMPBIN](../../build/reference/dumpbin-reference.md).

При компиляции программы с **/GL** и [/c](../../build/reference/c-compile-without-linking.md), чтобы создать выходной файл следует использовать параметр компоновщика/LTCG.

[/ ZI](../../build/reference/z7-zi-zi-debug-information-format.md) нельзя использовать с **/GL**

Формат файлов, формируемой с помощью **/GL** в текущей версии может быть для чтения в последующих версиях Visual C++. Не допускается поставка LIB-файл, состоящий из OBJ-файлы, которые были созданы с помощью **/GL** пока не будет готов к отправке копии LIB-файл для всех версий Visual C++ предполагается, что пользователям использовать теперь и в будущем.

OBJ-файлы, формируемой с помощью **/GL** и файлы предварительно скомпилированных заголовков не должны использоваться для создания в LIB-файл, если не будет связан LIB-файл на том же компьютере, на котором **/GL** OBJ-файле. Во время компоновки потребуются сведения из файла предкомпилированного заголовка OBJ-файле.

Дополнительные сведения о доступных оптимизациях и ограничения оптимизация всей программы, см. в разделе [/LTCG](../../build/reference/ltcg-link-time-code-generation.md).  **/GL** также делает профиль интерактивная оптимизация недоступна; см. в разделе/LTCG.  При компиляции для профильной оптимизации и необходимости упорядочивания функций на основе оптимизация, управляемая профилями, необходимо выполнять компиляцию с [/Gy](../../build/reference/gy-enable-function-level-linking.md) или параметр компилятора, который содержит в себе /Gy.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. См. в разделе [/LTCG (Создание кода во время компоновки)](../../build/reference/ltcg-link-time-code-generation.md) сведения о том, как указать **/GL** в среде разработки.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

1. См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WholeProgramOptimization%2A>.

## <a name="see-also"></a>См. также

[Параметры компилятора](../../build/reference/compiler-options.md)<br/>
[Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)