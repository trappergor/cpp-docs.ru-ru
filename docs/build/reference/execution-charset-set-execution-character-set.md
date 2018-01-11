---
title: "-выполнение-charset (набор символов исполнения набор) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- execution-charset
- /execution-charset
dev_langs: C++
helpviewer_keywords:
- /execution-charset compiler option
- -execution-charset compiler option
ms.assetid: 0e02f487-2236-45bc-95f3-5760933a8f96
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7cfb315c0dece0edc6228f70ed3900be80543cc7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="execution-charset-set-execution-character-set"></a>/ Execution-CharSet (задать выполнение кодировки)
Позволяет задать кодировку выполнения для исполняемого файла.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
/execution-charset:[IANA_name|.CPID]  
```  
  
## <a name="arguments"></a>Аргументы  
 **IANA_name**  
 Имя набора символов определен IANA.  
  
 **CPID**  
 Идентификатор кодовой страницы.  
  
## <a name="remarks"></a>Примечания  
 Можно использовать **/Execution-CharSet** параметр, чтобы указать набор символов исполнения. Кодировка выполнения имеет кодировку, используемую в тексте программы, которые подаются на вход на этапе компиляции в конце концов предварительной обработки действия. Этот набор символов используется для внутреннего представления любой строковых или символьных литералов в скомпилированном коде. Установите этот параметр для указания расширенной кодировки выполнения для использования при исходные файлы содержат символы, которые не может быть представлен в кодировке выполнения. Можно использовать либо IANA или имя набора символов ISO или точку (.) и идентификатором страницы десятичный формат цифра 3 – 5, чтобы указать кодировку для использования. Список поддерживаемых идентификаторы кодовой страницы и кодировку имен, см. в разделе [идентификаторы кодовой страницы](http://msdn.microsoft.com/library/windows/desktop/dd317756).  
  
 По умолчанию Visual Studio определяет метку порядка байтов, чтобы определить, если исходный файл в кодировке Юникод, например, UTF-16 или UTF-8. Если найдена метка порядка байтов отсутствуют, предполагается исходный файл кодируются с помощью текущей кодовой странице пользователя, если не указана кодировка имени или кодовой страницы с помощью **/Source-CharSet** параметр или   **/UTF-8** параметр. Visual Studio позволяет сохранить исходный код C++ с помощью любого из нескольких кодировки символов. Сведения об исходной и кодировка выполнения см. в разделе [кодировки](../../cpp/character-sets2.md) в документацию по языку.  
  
 Если вы хотите установить исходная кодировка и кодировка выполнения UTF-8, можно использовать **/UTF-8** параметр компилятора быстрого вызова. Аналогично заданию **/source-charset:utf-8 /execution-charset:utf-8** в командной строке. Любой из этих параметров также включает **/Validate-CharSet** параметр по умолчанию.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Установка данного параметра компилятора в среде разработки Visual Studio  
  
1.  Откройте диалоговое окно **Окна свойств** проекта. Дополнительные сведения см. в разделе [работа со свойствами проекта](../../ide/working-with-project-properties.md).  
  
2.  Разверните **свойства конфигурации**, **C/C++**, **командной строки** папки.  
  
3.  В **Дополнительные параметры**, добавьте **/Execution-CharSet** и задайте предпочтительной кодировки.  
  
4.  Выберите **ОК** для сохранения изменений.  
  
## <a name="see-also"></a>См. также  
 [Параметры компилятора](../../build/reference/compiler-options.md)   
 [Настройка параметров компилятора](../../build/reference/setting-compiler-options.md)   
 [/ Source-CharSet (задать исходной кодировки)](../../build/reference/source-charset-set-source-character-set.md)   
 [/ UTF-8 (задать источник и исполняемый объект кодировки UTF-8)](../../build/reference/utf-8-set-source-and-executable-character-sets-to-utf-8.md)   
 [/ Validate-CharSet (проверки для совместимых символов)](../../build/reference/validate-charset-validate-for-compatible-characters.md)