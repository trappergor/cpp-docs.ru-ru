---
title: "Программирование с использованием CComBSTR (ATL) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- CComBSTR class, programming with
- Unicode, using CComBSTR [ATL]
ms.assetid: d3bd0851-d132-4be9-9c4c-6ccba17acb2b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f8f496dd73c2d15f8f78ddbdc205f31a8520c674
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="programming-with-ccombstr-atl"></a>Программирование с использованием CComBSTR (ATL)
Класс ATL [CComBSTR](../atl/reference/ccombstr-class.md) предоставляет оболочку `BSTR` тип данных. Хотя `CComBSTR` — это эффективное средство, существует несколько ситуаций, требующих осторожность.  
  
-   [Проблемы преобразования](#programmingwithccombstr_conversionissues)  
  
-   [Область проблемы](#programmingwithccombstr_scopeissues)  
  
-   [Явное освобождение объектов CComBSTR](#programmingwithccombstr_explicitlyfreeing)  
  
-   [Использование CComBSTR объектов в циклах](#programmingwithccombstr_usingloops)  
  
-   [Проблемы утечки памяти](#programmingwithccombstr_memoryleaks)  
  
##  <a name="programmingwithccombstr_conversionissues"></a>Проблемы преобразования  
 Несмотря на то что несколько `CComBSTR` методы автоматически преобразует аргумент строки ANSI в Юникод, методов, всегда будет возвращать строки формата Юникод. Чтобы преобразовать выходной строки ANSI, используйте класс ATL преобразования. Дополнительные сведения о преобразовании классы ATL см. в разделе [ATL и MFC макросы преобразования строк](reference/string-conversion-macros.md).  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#114](../atl/codesnippet/cpp/programming-with-ccombstr-atl_1.cpp)]  
  
 При использовании строкового литерала для изменения `CComBSTR` , используйте строки расширенных символов. Это позволит снизить ненужные преобразования.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#115](../atl/codesnippet/cpp/programming-with-ccombstr-atl_2.cpp)]  
  
##  <a name="programmingwithccombstr_scopeissues"></a>Область проблемы  
 Как и в случае с любой обретают класс `CComBSTR` , чтобы освободить ресурсы, когда он покидает область действия. Если функция возвращает указатель на `CComBSTR` строки, это может вызвать проблемы, как будет ссылаться на указатель памяти, который уже был освобожден. В таких случаях **копирования** метода, как показано ниже.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#116](../atl/codesnippet/cpp/programming-with-ccombstr-atl_3.cpp)]  
  
##  <a name="programmingwithccombstr_explicitlyfreeing"></a>Явное освобождение объектов CComBSTR  
 Можно явно освободить строку, содержащихся в `CComBSTR` перед объект выходит из области. Если строка освобождается, `CComBSTR` недопустимый объект.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#117](../atl/codesnippet/cpp/programming-with-ccombstr-atl_4.cpp)]  
  
##  <a name="programmingwithccombstr_usingloops"></a>Использование CComBSTR объектов в циклах  
 Как `CComBSTR` класс выделяет буфер для выполнения определенных операций, таких как `+=` оператор или **Append** метод, не рекомендуется выполнять строками в непрерывном цикле. В таких ситуациях `CStringT` обеспечивает более высокую производительность.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#118](../atl/codesnippet/cpp/programming-with-ccombstr-atl_5.cpp)]  
  
##  <a name="programmingwithccombstr_memoryleaks"></a>Проблемы утечки памяти  
 Передав адрес инициализированный `CComBSTR` мог функционировать как **[out]** параметр вызывает утечку памяти.  
  
 В следующем примере строки, выделенные для хранения строки `"Initialized"` произошла утечка при функция `MyGoodFunction` заменяет строку.  
  
 [!code-cpp[NVC_ATL_Utilities#119](../atl/codesnippet/cpp/programming-with-ccombstr-atl_6.cpp)]  
  
 Во избежание утечки вызвать **пустой** метод на существующие `CComBSTR` объектов перед их передачей адрес как **[out]** параметра.  
  
 Обратите внимание, что тот же код не вызовет утечку в случае параметра функции **[в, out]**.  
  
## <a name="see-also"></a>См. также  
 [Основные понятия](../atl/active-template-library-atl-concepts.md)   
 [Класс CStringT](../atl-mfc-shared/reference/cstringt-class.md)   
 [wstring](../standard-library/basic-string-class.md)   
 [Макросы преобразования строк](../atl/reference/string-conversion-macros.md)

