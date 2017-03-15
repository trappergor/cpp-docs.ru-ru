---
title: "CString Argument Passing | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "argument passing [C++]"
  - "argument passing [C++], C strings"
  - "arguments [C++], передача"
  - "CString objects, передача аргументов"
  - "функции [C++], strings as input/output"
  - "передача аргументов, C strings"
  - "string arguments"
  - "строки [C++], as function input/output"
ms.assetid: a67bebff-edf1-4cf4-bbff-d1cc6a901099
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CString Argument Passing
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В этой статье описывается, как передать объекты [CString](../atl-mfc-shared/reference/cstringt-class.md) к функциям и возврата объектов `CString` от функций.  
  
##  <a name="_core_cstring_argument.2d.passing_conventions"></a> Соглашения Аргумент\- Передавая CString  
 При определении интерфейса класса необходимо указать аргумент\- передавая о вызовах для функций\-членов.  Некоторые стандартные правила для передачи и возврата объектов `CString`.  Если следовать правилам, описанными в [Строки как входные данные функции](#_core_strings_as_function_inputs) и [Строки как выходные данные функции](#_core_strings_as_function_outputs), будет иметь эффективный, правильный код.  
  
##  <a name="_core_strings_as_function_inputs"></a> Строки как входные данные функции  
 Наиболее эффективный и наиболее безопасный способ использования объекта `CString` в функциях, вызванных передать объект `CString` функции.  Несмотря на имени, объект `CString` не сохраняется строка внутри c. вставка строки как стили, которая имеет нулевой завершающий символ.  Вместо этого объект `CString` содержит тщательную отслеживание числа символов он содержит.  Having `CString` реализуйте указатель `LPCTSTR` null\- готовая строка небольшой объем работы, который может стать значительно если код должен выполнить его постоянным.  Результатом является временным, поскольку любое изменение содержимого `CString` делает недействительным старые копии указателя `LPCTSTR`.  
  
 Он имеет смысл в некоторых случаях предоставить c \- вставьте строку стиля.  Например, могут быть ситуация, когда вызванная функция записана в C\# и не поддерживают объекты.  В этом случае coerce \- параметр `CString` к `LPCTSTR` и функции, производящие c \- стиль null\- готовая строка.  Также можно перейти другое направление и создания объекта `CString` с помощью конструктора, который принимает `CString` c. вставка параметр стиля строки.  
  
 Если содержимое строки изменением функцией, объявите параметр как nonconstant ссылка `CString` \(**CString&**\).  
  
##  <a name="_core_strings_as_function_outputs"></a> Строки как выходные данные функции  
 Обычно можно вернуться объекты `CString` от функций поскольку объекты `CString` следовать семантике значения как типы\-примитивы.  Для возвращения типа string, доступное только для чтения, используйте константу ссылку `CString` \(**const CString&**\).  В следующем примере показано использование параметров и возвращаемых типов `CString`:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#197](../atl-mfc-shared/codesnippet/CPP/cstring-argument-passing_1.cpp)]  
  
 [!code-cpp[NVC_ATLMFC_Utilities#198](../atl-mfc-shared/codesnippet/CPP/cstring-argument-passing_2.cpp)]  
  
## См. также  
 [Строки](../atl-mfc-shared/strings-atl-mfc.md)