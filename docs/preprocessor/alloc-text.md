---
title: "alloc_text | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc-pragma.alloc_text
- alloc_text_CPP
dev_langs: C++
helpviewer_keywords:
- alloc_text pragma
- pragmas, alloc_text
ms.assetid: 1fd7be18-e4f7-4f70-b079-6326f72b871a
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e877f747bc825faac38c3557b52e0f0969257208
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="alloctext"></a>alloc_text
Назначает имя разделу кода, в котором должны располагаться заданные определения функций. Директива pragma должна быть между декларатором функции и определением функции для именованных функций.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
#pragma alloc_text( "  
textsection  
", function1, ... )  
```  
  
## <a name="remarks"></a>Примечания  
 **Alloc_text** pragma не обрабатывает функций-членов C++ и перегруженные функции. Это применимо только к функциям, которые объявлены с компоновкой C — то есть, функций, объявленных с **extern «C»** спецификация компоновки. При попытке использовать эту директиву pragma в функции с компоновкой C++ возникнет ошибка компилятора.  
  
 С момента адресации с помощью функции `__based` не поддерживается, указания местоположения разделов необходимо использование **alloc_text** pragma. Имя, указанное в *textsection* должны быть заключены в двойные кавычки.  
  
 **Alloc_text** директива pragma должна располагаться после всех объявлений указанных функций и до определения этих функций.  
  
 Функции, на которые ссылается **alloc_text** pragma должен быть определен в том же модуле, что и директива pragma. В противном случае, если неопределенная функция впоследствии будет скомпилирована в другом разделе текста, ошибка может не быть перехвачена. Хотя в большинстве случаев программа будет выполняться правильно, функция не будет выделена в нужных разделах.  
  
 Другие ограничения на **alloc_text** таковы:  
  
-   Она не может использоваться внутри функции.  
  
-   Она должна использоваться после объявления функции, но перед ее определением.  
  
## <a name="see-also"></a>См. также  
 [Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)