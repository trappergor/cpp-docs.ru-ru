---
title: '&lt;в разделе&gt; (Visual C++) | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- <see>
- see
dev_langs:
- C++
helpviewer_keywords:
- <see> C++ XML tag
- see C++ XML tag
ms.assetid: 20ef66f4-b278-45cf-8613-63919edf5720
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a03dd56320b948d47c765f253bf3e6b706ed2b56
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ltseegt-visual-c"></a>&lt;в разделе&gt; (Visual C++)
Тег \<see> позволяет задать ссылку из текста. Используйте [ \<seealso >](../ide/seealso-visual-cpp.md) для указания текста, который может отображаться в разделе см. также.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
<see cref="member"/>  
```  
  
#### <a name="parameters"></a>Параметры  
 `member`  
 Ссылка на член или поле, которые доступны для вызова из текущей среды компиляции.  Заключите имя в одинарные или двойные кавычки.  
  
 Компилятор проверяет, что данный элемент кода существует и устраняет `member` имени элемента в выходных данных XML.  Если компилятору не удается найти `member`, он выдает предупреждение.  
  
## <a name="remarks"></a>Примечания  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md).  
  
 В разделе [ \<сводки >](../ide/summary-visual-cpp.md) пример использования \<см >.  
  
 Компилятор Visual C++ будет пытаться разрешить ссылки cref за один проход по комментариям документации.  Поэтому если при использовании правил поиска C++ компилятор не найдет символ, ссылка будет помечена как не разрешенная. В разделе [ \<seealso >](../ide/seealso-visual-cpp.md) для получения дополнительной информации.  
  
## <a name="example"></a>Пример  
 Следующий пример показывает, как сделать cref ссылка на универсальный тип, таким образом, что компилятор будет разрешить ссылку на.  
  
```  
// xml_see_cref_example.cpp  
// compile with: /LD /clr /doc  
// the following cref shows how to specify the reference, such that,  
// the compiler will resolve the reference  
/// <see cref="C{T}">  
/// </see>  
ref class A {};  
  
// the following cref shows another way to specify the reference,   
// such that, the compiler will resolve the reference  
/// <see cref="C < T >"/>  
  
// the following cref shows how to hard-code the reference  
/// <see cref="T:C`1">  
/// </see>  
ref class B {};  
  
/// <see cref="A">  
/// </see>  
/// <typeparam name="T"></typeparam>  
generic<class T>  
ref class C {};  
```  
  
## <a name="see-also"></a>См. также  
 [Документация XML](../ide/xml-documentation-visual-cpp.md)