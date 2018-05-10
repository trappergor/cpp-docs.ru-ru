---
title: Директивы pragma в С | Документация Майкрософт
ms.custom: ''
ms.date: 01/29/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- pragmas, C/C++
ms.assetid: 3d6d36b4-d565-4632-a4cd-e39aeaded5ad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a87a6518eec495961d1f8d40c625e589db01bd3b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="c-pragmas"></a>Прагмы C

**Блок, относящийся только к системам Microsoft**

Директива *pragma* указывает компилятору выполнить определенное действие во время компиляции. Директивы pragma зависят от компилятора. Например, чтобы задать оптимизации для выполнения в программе, можно использовать директиву pragma **optimize**. Ниже перечислены директивы pragma Microsoft C.

|||||
|-|-|-|-|
|**alloc_text**|**data_seg**|**inline_recursion**|**setlocale**|
|**auto_inline**|**function**|**intrinsic**|**warning**|
|**check_stack**|**hdrstop**|**message**||
|**code_seg**|**include_alias**|**optimize**||
|**comment**|**inline_depth**|**pack**||

Описание директив pragma для компилятора Microsoft C см. в разделе [Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md).

 **Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Файлы с исходным кодом и исходные программы](../c-language/source-files-and-source-programs.md)  
