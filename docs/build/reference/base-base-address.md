---
title: "-BASE (базовый адрес) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /base
- VC.Project.VCLinkerTool.BaseAddress
dev_langs: C++
helpviewer_keywords:
- base addresses [C++]
- programs [C++], preventing relocation
- semicolon [C++], specifier
- -BASE linker option
- key address size
- environment variables [C++], LIB
- programs [C++], base address
- LIB environment variable
- BASE linker option
- DLLs [C++], linking
- /BASE linker option
- '@ symbol for base address'
- executable files [C++], base address
- at sign symbol for base address
ms.assetid: 00b9f6fe-0bd2-4772-a69c-7365eb199069
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9ddf399757d881484817be676ca3077b4fc21709
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="base-base-address"></a>/BASE (базовый адрес)
```  
/BASE:{address[,size] | @filename,key}  
```  
  
 / Параметр BASE задает базовый адрес программы, переопределяя расположение по умолчанию для .exe или DLL-файл. Базовый адрес по умолчанию для файла .exe — 0x400000 для 32-разрядных образов или 0x140000000 относятся для 64-разрядных образов. Для DLL-Библиотеки базовый адрес по умолчанию — 0x10000000 для 32-разрядных образов или 0x180000000 для 64-разрядных образов. В операционных системах, которые не поддерживают технологию address space макета randomization (ASLR) или когда был установлен параметр внесение операционная система сначала пытается загрузить программу в его указанном или базовый адрес по умолчанию. Если недостаточно места не существует, система использует программы. Для предотвращения перемещения используйте [/FIXED](../../build/reference/fixed-fixed-base-address.md) параметр.  
  
 Компоновщик выдает ошибку, если *адрес* не кратен 64 КБ. При необходимости можно указать размер программы; Компоновщик выдает предупреждение, если программа не может поместиться в указанный размер.  
  
 В командной строке другой способ указать базовый адрес — с помощью файла ответов базовый адрес. Файл ответа базовый адрес является текстовый файл, содержащий базовые адреса и необязательный размеры всех библиотек DLL, которые будут использоваться программой и текст уникальный ключ для каждого базового адреса. Чтобы указать базовый адрес, используя файл ответов, используйте знак (@) и имя файла ответов, *filename*, а затем с помощью символа запятой, то `key` значение базового адреса для использования в файле. Компоновщик будет искать *filename* либо по указанному пути или если путь не указан, в каталогах, указанных в переменной среды LIB. В каждой строке *filename* представляет одну библиотеку DLL и имеет следующий синтаксис:  
  
```  
  
key address [size] ;comment  
```  
  
 `key` Представляет собой строку алфавитно-цифровых символов и не учитывается регистр. Обычно это имя для библиотеки DLL, но это не обязательно. `key` Следуют базового *адрес* в языке C, шестнадцатеричном или десятичном формате и необязательный максимально `size`. Все три аргумента разделяются пробелами или знаками табуляции. Компоновщик выдает предупреждение, если указанный `size` меньше, чем виртуальное адресное пространство, используемые программой. Объект `comment` указан точкой с запятой (;) и может быть на том же или отдельной строке. Компоновщик игнорирует весь текст после точки с запятой в конец строки. В этом примере показана часть такой файл:  
  
```  
main   0x00010000    0x08000000    ; for PROJECT.exe  
one    0x28000000    0x00100000    ; for DLLONE.DLL  
two    0x28100000    0x00300000    ; for DLLTWO.DLL  
```  
  
 Если файл, содержащий эти строки, называется DLLS.txt, следующая команда применяются эти сведения.  
  
```  
link dlltwo.obj /dll /base:@dlls.txt,two  
```  
  
## <a name="remarks"></a>Примечания  
 По соображениям безопасности рекомендуется использовать [/DYNAMICBASE](../../build/reference/dynamicbase-use-address-space-layout-randomization.md) , а не базового адреса для исполняемые файлы. Это приводит к возникновению ошибки исполняемый образ, который может быть случайным образом перемещен во время загрузки с помощью функции Windows адрес макет пространства randomization (ASLR). Параметр/DYNAMICBASE включен по умолчанию.  
  
 Еще один способ задания базового адреса — с помощью *БАЗОВОГО* аргумент в [имя](../../build/reference/name-c-cpp.md) или [БИБЛИОТЕКИ](../../build/reference/library.md) инструкции. / Base и [/DLL](../../build/reference/dll-build-a-dll.md) параметры вместе эквивалентны **БИБЛИОТЕКИ** инструкции.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [задание свойств проекта Visual C++](../../ide/working-with-project-properties.md).  
  
2.  Разверните **компоновщика** папки.  
  
3.  Выберите **Дополнительно** страницу свойств.  
  
4.  Изменить **базовый адрес** свойство.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом  
  
-   См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.BaseAddress%2A>.  
  
## <a name="see-also"></a>См. также  
 [Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)   
 [Параметры компоновщика](../../build/reference/linker-options.md)