---
title: -GL (оптимизация всей программы) | Документы Microsoft
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
ms.openlocfilehash: ce972b6e7254ad7454f8e8799283588f0fdd5270
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="gl-whole-program-optimization"></a>/GL (оптимизация всей программы)
Включает оптимизацию всей программы.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/GL[-]  
```  
  
## <a name="remarks"></a>Примечания  
 Оптимизация всей программы позволяет компилятору выполнять оптимизацию с помощью информации о всех модулях в программе. Без оптимизации всей программы, выполняемых операций оптимизации для каждого отдельного модуля (объекта компиляции).  
  
 Оптимизация всей программы по умолчанию отключена и должно быть явно включено. Однако это также можно явно отключить его с **/GL-**.  
  
 Сведения о всех модулей компилятор выполнять следующие действия:  
  
-   Оптимизируйте использование регистров за границами функций.  
  
-   Лучше всего выполняют отслеживать изменение глобальных данных, что позволит уменьшить количество загрузки и сохранения.  
  
-   Лучше всего выполняют отслеживания разыменования возможные наборы элементов, измененных при помощи указателя, уменьшение количества загрузки и сохранения.  
  
-   Встроенные функции в модуле даже в том случае, если функция определена в другом модуле.  
  
 OBJ-файлы, формируемой с помощью **/GL** не будут доступны таким средствам компоновщика, как [EDITBIN](../../build/reference/editbin-reference.md) и [DUMPBIN](../../build/reference/dumpbin-reference.md).  
  
 При компиляции программы с **/GL** и [/c](../../build/reference/c-compile-without-linking.md), следует использовать параметр компоновщика/LTCG для создания выходного файла.  
  
 [/ ZI](../../build/reference/z7-zi-zi-debug-information-format.md) не может использоваться с **/GL**  
  
 Формат файлов, формируемой с помощью **/GL** в текущей версии могут стать нечитаемыми последующими версиями Visual C++. Не следует поставлять LIB-файл, состоящий из OBJ-файлы, которые были созданы при помощи **/GL** Если вы готовы пойти на поставку копии LIB-файл для всех версий Visual C++ предполагается, что пользователи, сейчас и в будущем.  
  
 OBJ-файлы, формируемой с помощью **/GL** и файлы предкомпилированных заголовков не должны использоваться для построения LIB-файл, если не будет связан LIB-файл на том же компьютере, который создал **/GL** OBJ-файле. Сведения из файла предкомпилированного заголовка OBJ-файле необходимо указать во время компоновки.  
  
 Дополнительные сведения о доступных оптимизациях и ограничениях оптимизации всей программы см. в разделе [/LTCG](../../build/reference/ltcg-link-time-code-generation.md).  **/GL** также делает профиль возможностей оптимизации доступных; см.  При компиляции для профильной оптимизации и необходимости упорядочивания функций на основе оптимизация, управляемая профилями, необходимо выполнять компиляцию с [/Gy](../../build/reference/gy-enable-function-level-linking.md) или параметр компилятора, подразумевающий параметр/Gy.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  В разделе [/LTCG (Создание кода во время компоновки)](../../build/reference/ltcg-link-time-code-generation.md) сведения о том, как указать **/GL** в среде разработки.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
1.  См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.WholeProgramOptimization%2A>.  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)