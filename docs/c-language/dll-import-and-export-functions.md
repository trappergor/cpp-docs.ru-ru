---
title: "Функции импорта и экспорта DLL | Документация Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- DLLs [C++], importing
- dllimport attribute [C++], storage-class attribute
- DLL exports [C++]
- declaring functions, with dllexport and dllimport
- extended storage-class attributes
- dllexport attribute [C++], storage-class attribute
ms.assetid: 08d164b9-770a-4e14-afeb-c6f21d9e33e4
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b79856a524cb9693d43d9929b22d6c63db5ba319
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="dll-import-and-export-functions"></a>Функции импорта и экспорта DLL
**Блок, относящийся только к системам Microsoft**  
  
 Наиболее полную и актуальную информацию по этой теме можно найти в статье [dllexport, dllimport](../cpp/dllexport-dllimport.md).  
  
 Модификаторы класса хранения **dllimport** и `dllexport` — это расширения языка С для систем Microsoft. Эти модификаторы явным образом определяют интерфейс библиотеки DLL к ее клиенту (исполняемому файлу или другой библиотеке DLL). Объявление функции в качестве `dllexport` позволяет обойтись без файла определения модуля (.DEF). Кроме того, модификаторы **dllimport** и `dllexport` можно использовать с данными и объектами.  
  
 Модификаторы класса хранения **dllimport** и `dllexport` должны использоваться с ключевым словом расширенного синтаксиса атрибутов `__declspec`, как показано в следующем примере:  
  
```  
#define DllImport   __declspec( dllimport )  
#define DllExport   __declspec( dllexport )  
  
DllExport void func();  
DllExport int i = 10;  
DllExport int j;  
DllExport int n;  
```  
  
 Дополнительные сведения о синтаксисе расширенных модификаторов класса хранения см. в статье [C Extended Storage-Class Attributes](../c-language/c-extended-storage-class-attributes.md) (Расширенные атрибуты классов хранения C).  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Определения функций в C](../c-language/c-function-definitions.md)