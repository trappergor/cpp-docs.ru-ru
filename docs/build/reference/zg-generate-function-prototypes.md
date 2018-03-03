---
title: "-Zg (Создание прототипов функций) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /zg
dev_langs:
- C++
helpviewer_keywords:
- Zg compiler option [C++]
- /Zg compiler option [C++]
- function prototypes, generate function prototypes compiler option
- -Zg compiler option [C++]
- generate function prototypes compiler option
ms.assetid: c8df1b46-24ff-46f2-8356-e0a144b21dd2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 03e42c32806bbe7142b8d4d03e2f0974eeacdf84
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="zg-generate-function-prototypes"></a>/Zg (создание прототипов функций)
Удалено. Для каждой функции, определенной в исходном файле, создает прототип; компиляция исходного файла при этом не производится.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/Zg  
```  
  
## <a name="remarks"></a>Примечания  
 Этот параметр компилятора больше не доступен. Он был удален в Visual C++ 2015. Эта страница сохраняется для пользователей более ранних версий Visual C++.  
  
 В состав прототипа функции входит тип возвращаемого значения функции и список типов аргументов. Список типов аргументов создается на основе типов формальных параметров функции. Все прототипы функций, присутствующие в исходном файле, пропускаются.  
  
 Список прототипов выводится в стандартные выходные данные. Этот список может быть полезен для проверки совместимости реальных аргументов и формальных параметров функции. Список можно сохранить, перенаправив стандартный поток вывода в файл. После этого можно использовать оператор **#include** , чтобы включить список прототипов в состав исходного файла. Это заставит компилятор выполнять проверку типов аргументов.  
  
 Если при использовании параметра **/Zg** в программе используются формальные параметры, имеющие тип структуры, перечисления или объединения (или указателей на подобные типы), то в объявлении всех таких структур, перечислений и объединений должен присутствовать тег (имя). В следующем примере имя тега — `MyStruct`:  
  
```C  
// Zg_compiler_option.c  
// compile with: /Zg  
typedef struct MyStruct { int i; } T2;  
void f2(T2 * t) {}  
```  
  
 **/Zg** параметр перестал поддерживаться в Visual Studio 2005 и был удален в Visual Studio 2015. Компилятор Visual C++ была удалена поддержка более старые, C-стиле кода. Список параметров компилятора см. в разделе **нерекомендуемые и удаленные параметры компилятора** в [параметры компилятора, упорядоченные по категориям](../../build/reference/compiler-options-listed-by-category.md).  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Откройте папку **C/C++** .  
  
3.  Выберите страницу свойств **Командная строка** .  
  
4.  Введите параметр компилятора в поле **Дополнительные параметры** .  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Установка данного параметра компилятора программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>.  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)