---
title: '&lt;para&gt; (Visual C++) | Документы Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- <para>
- para
dev_langs:
- C++
helpviewer_keywords:
- <para> C++ XML tag
- para C++ XML tag
ms.assetid: 35f2a1b3-bc14-4f13-bcb0-c39ccbf74d59
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1ebf50e4672ee2a3398f6c484c42f8e36f231169
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33325121"
---
# <a name="ltparagt-visual-c"></a>&lt;para&gt; (Visual C++)
Тег \<para> используется внутри другого тега, например [\<summary>](../ide/summary-visual-cpp.md), [\<remarks>](../ide/remarks-visual-cpp.md) или [\<returns>](../ide/returns-visual-cpp.md), и позволяет добавить к тексту структуру.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
<para>content</para>  
```  
  
#### <a name="parameters"></a>Параметры  
 `content`  
 Текст абзаца.  
  
## <a name="remarks"></a>Примечания  
 Чтобы обработать и сохранить комментарии документации в файл, при компиляции необходимо использовать параметр [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md).  
  
## <a name="example"></a>Пример  
 В разделе [\<summary>](../ide/summary-visual-cpp.md) можно найти пример использования тега \<para>.  
  
## <a name="see-also"></a>См. также  
 [Документация XML](../ide/xml-documentation-visual-cpp.md)