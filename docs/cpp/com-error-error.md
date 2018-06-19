---
title: _com_error::Error | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_error::Error
- Error
dev_langs:
- C++
helpviewer_keywords:
- Error method [C++]
ms.assetid: b53a15fd-198e-4276-afcd-13439c4807f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 02afac78de5eb5908d477f8503ceeebffe46f672
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32412586"
---
# <a name="comerrorerror"></a>_com_error::Error
**Блок, относящийся только к системам Microsoft**  
  
 Получает элемент `HRESULT`, переданный конструктору.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
HRESULT Error( ) const throw( );  
  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Необработанный элемент `HRESULT`, переданный в конструктор.  
  
## <a name="remarks"></a>Примечания  
 Получает инкапсулированный элемент `HRESULT` в объекте `_com_error`.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Класс _com_error](../cpp/com-error-class.md)