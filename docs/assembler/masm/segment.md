---
title: "СЕГМЕНТ | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- SEGMENT
dev_langs:
- C++
helpviewer_keywords:
- SEGMENT directive
ms.assetid: e6f68367-6714-4f06-a79c-edfa88014430
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 253c3b389bd0411e6b5096e914b6a844c8f40805
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2018
---
# <a name="segment"></a>SEGMENT
Определяет сегмент программы вызывается *имя* наличие атрибутов сегмента  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
   name SEGMENT [[READONLY]] [[align]] [[combine]] [[use]] [[characteristics]] ALIAS(string) [['class']]  
statements  
name ENDS  
```  
  
#### <a name="parameters"></a>Параметры  
 *align*  
 Диапазон адресов памяти, из которых можно выбрать начальный адрес сегмента. Тип выравнивания может быть одним из следующих:  
  
|Выравнивание типа|Начальный адрес|  
|----------------|----------------------|  
|**BYTE**|Следующий адрес доступных байтов.|  
|**WORD**|Следующий адрес доступных word (2 байта на word).|  
|**DWORD**|Следующий адрес доступных двойное слово (4 байта на двойное слово).|  
|**АБЗАЦ**|Адрес следующего абзаца доступные (16 байт на абзаца).|  
|**PAGE**|Следующий адрес страницы (256 байт на страницу).|  
|**ALIGN**(*n*)|Далее доступных *n*th байтам адреса. См. раздел Примечания для получения дополнительной информации.|  
  
 Если этот параметр не указан, **PARA** используется по умолчанию.  
  
 *combine*  
 **ОТКРЫТЫЙ**, **стека**, **Общие**, **памяти**, **в *** адрес*, **ЗАКРЫТЫЙ**  
  
 *use*  
 **USE16**, **USE32**, **FLAT**  
  
 `characteristics`  
 **Сведения о**, **чтения**, **записи**, **EXECUTE**, **SHARED**, **NOPAGE**, **NOCACHE**, и **ОТМЕНИТЬ**  
  
 Они поддерживаются только для COFF и соответствуют характеристики раздел COFF похожим именем (например, **SHARED** соответствует IMAGE_SCN_MEM_SHARED). ЧТЕНИЕ устанавливает флаг IMAGE_SCN_MEM_READ. Флаг используется только для чтения за раздел, чтобы снять флаг IMG_SCN_MEM_WRITE. При наличии `characteristics` настраиваются, используемые по умолчанию параметры не используются и действуют только флаги заданного программистом.  
  
 `ALIAS(` `string` `)`  
 Эта строка используется как имя раздела в передаваемый объект COFF.  Создает несколько разделов с внешних с одинаковым именем, различающихся имен MASM сегмента.  
  
 Не поддерживается с **/OMF**.  
  
 `class`  
 Определяет, как следует объединить и упорядоченных собранный файл сегментов. Допустимые значения:, `'DATA'`, `'CODE'`, `'CONST'` и `'STACK'`  
  
## <a name="remarks"></a>Примечания  
 Для `ALIGN(n)`, `n` может быть любой степени числа 2 от 1 до 8192; не поддерживается с **/OMF**.  
  
## <a name="see-also"></a>См. также  
 [Справочник по директивам](../../assembler/masm/directives-reference.md)