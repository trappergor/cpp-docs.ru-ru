---
title: "Синтаксис командной строки компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- syntax, CL compiler command line
- cl.exe compiler, command-line syntax
ms.assetid: acba2c1c-0803-4a3a-af25-63e849b930a2
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7fb89aca1990d44d7ef62ea76788b38e8ffa1d6d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-command-line-syntax"></a>Синтаксис командной строки компилятора
В командной строке компилятора используется следующий синтаксис:  
  
```  
CL [option...] file... [option | file]... [lib...] [@command-file] [/link link-opt...]  
```  
  
 В следующей таблице описаны ввод команду CL.  
  
|Ввод|Значение|  
|-----------|-------------|  
|*параметр*|Один или несколько [параметров CL](../../build/reference/compiler-options.md). Обратите внимание, что все параметры применяются ко всем файлам указанного источника. Параметры задаются путем косой черты (/) или дефис (-). Если параметр принимает аргумент в описании параметра указывается, является ли пробел между параметром и аргументы. Имена параметров (за исключением параметра/Help) чувствительны к регистру. В разделе [порядок параметров CL](../../build/reference/order-of-cl-options.md) для получения дополнительной информации.|  
|`file`|Имя одного или нескольких исходных файлов, OBJ-файлов или библиотек. CL компилирует исходные файлы и передает компоновщику имена OBJ-файлы и библиотеки. В разделе [синтаксис имен файлов CL](../../build/reference/cl-filename-syntax.md) для получения дополнительной информации.|  
|*LIB*|Одно или несколько имен библиотеки. Компилятор передает эти имена компоновщику.|  
|*командный файл*|Файл, содержащий несколько параметров и имен файлов. В разделе [командные файлы компилятора CL](../../build/reference/cl-command-files.md) для получения дополнительной информации.|  
|*Включить ссылку*|Один или несколько [параметры компоновщика](../../build/reference/linker-options.md). Компилятор передает эти параметры компоновщику.|  
  
 Можно указать любое количество параметров, имен файлов и библиотек, до тех пор, пока количество символов в командной строке не превышает 1024, ограничение определяется операционной системой.  
  
 Дополнительные сведения о значении cl.exe, в разделе [возвращают значение cl.exe](../../build/reference/return-value-of-cl-exe.md) .  
  
> [!NOTE]
>  Ограничение ввода командной строки 1024 символов не обязательно остаются неизменными в будущих версиях Windows.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)   
 [Параметры компилятора](../../build/reference/compiler-options.md)