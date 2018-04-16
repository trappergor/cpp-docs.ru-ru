---
title: -utf 8 (задать источник и исполняемый файл кодировки UTF-8) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- /utf-8
dev_langs:
- C++
helpviewer_keywords:
- /utf-8 compiler option
ms.assetid: f0e1f3cb-6cae-46eb-9483-04ed13d9b504
caps.latest.revision: 3
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 592cba779113a6658b40d0dc3f855f53fa3d170c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="utf-8-set-source-and-executable-character-sets-to-utf-8"></a>/ UTF-8 (задать источник и исполняемый объект кодировки UTF-8)
Указывает задания исходной кодировки и кодировки выполнения как UTF-8.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/utf-8  
```  
  
## <a name="remarks"></a>Примечания  
 Можно использовать **/UTF-8** параметр, чтобы указать источник и выполнения кодировки в кодировке с помощью UTF-8. Аналогично заданию **/source-charset:utf-8 /execution-charset:utf-8** в командной строке. Любой из этих параметров также включает **/Validate-CharSet** параметр по умолчанию. Список поддерживаемых идентификаторы кодовой страницы и кодировку имен, см. в разделе [идентификаторы кодовой страницы](http://msdn.microsoft.com/library/windows/desktop/dd317756).  
  
 По умолчанию Visual Studio определяет метку порядка байтов, чтобы определить, если исходный файл в кодировке Юникод, например, UTF-16 или UTF-8. Если найдена метка порядка байтов отсутствуют, предполагается исходный файл кодируются с помощью текущей кодовой странице пользователя, пока не задана кодовая страница с помощью **/UTF-8** или **/Source-CharSet** параметр. Visual Studio позволяет сохранить исходный код C++ с помощью любого из нескольких кодировки символов. Сведения об исходной и кодировка выполнения см. в разделе [кодировки](../../cpp/character-sets2.md) в документацию по языку.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Окна свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Разверните **свойства конфигурации**, **C/C++**, **командной строки** папки.  
  
3.  В **Дополнительные параметры**, добавьте **/UTF-8** и задайте предпочтительной кодировки.  
  
4.  Выберите **ОК** для сохранения изменений.  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)   
 [/ Execution-CharSet (задать выполнение кодировки)](../../build/reference/execution-charset-set-execution-character-set.md)   
 [/ Source-CharSet (задать исходной кодировки)](../../build/reference/source-charset-set-source-character-set.md)   
 [/ Validate-CharSet (проверки для совместимых символов)](../../build/reference/validate-charset-validate-for-compatible-characters.md)