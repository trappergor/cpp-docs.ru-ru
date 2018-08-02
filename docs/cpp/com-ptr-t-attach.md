---
title: _com_ptr_t::Attach | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_ptr_t::Attach
dev_langs:
- C++
helpviewer_keywords:
- COM interfaces, attach pointer
- Attach method [C++]
ms.assetid: 94c18e0a-06be-4ca7-bdaf-cd54ec0a645e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c48da9a0ff3b9cadf0b7e228f3108277154e8417
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/01/2018
ms.locfileid: "39402888"
---
# <a name="comptrtattach"></a>_com_ptr_t::Attach
**Блок, относящийся только к системам Microsoft**  
  
 Инкапсулирует необработанный указатель на интерфейс для типа этого интеллектуального указателя.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void Attach( Interface* pInterface ) throw( );  
void Attach( Interface* pInterface, bool fAddRef ) throw( );  
```  
  
#### <a name="parameters"></a>Параметры  
 *pInterface*  
 Необработанный указатель на интерфейс.  
  
 *fAddRef*  
 Если он имеет значение TRUE, затем `AddRef` вызывается. Если он имеет значение FALSE, `_com_ptr_t` объект принимает владение базовым указателем на интерфейс без вызова `AddRef`.  
  
## <a name="remarks"></a>Примечания  
  
-   **Присоединение (***pInterface***)** `AddRef` не вызывается. Право на владение интерфейсом передается данному объекту `_com_ptr_t`. `Release` вызывается для уменьшения счетчика ссылок для ранее инкапсулированного указателя.  
  
-   **Присоединение (***pInterface* **,***fAddRef***)** Если *fAddRef* имеет значение TRUE, `AddRef`вызывается следует выполнить приращение счетчика ссылок для указателя инкапсулированного интерфейса.       Если *fAddRef* имеет значение FALSE, это `_com_ptr_t` объект принимает владение базовым указателем на интерфейс без вызова `AddRef`. `Release` вызывается для уменьшения счетчика ссылок для ранее инкапсулированного указателя.  
  
 **Завершение блока, относящегося только к системам Майкрософт**  
  
## <a name="see-also"></a>См. также  
 [Класс _com_ptr_t](../cpp/com-ptr-t-class.md)