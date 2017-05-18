---
title: "Перечисление UICheckState | Документы Microsoft"
ms.custom: 
ms.date: 04/03/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- afxwinforms/uicheckstate
dev_langs:
- C++
helpviewer_keywords:
- uicheckstate enumeration
ms.assetid: 2ac0098c-20e7-410c-9685-5ead5cb02b63
caps.latest.revision: 17
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: b943ef8dd652df061965fe81ecc9c08115636141
ms.openlocfilehash: d30ddee047597750d4627efee8ec8d9e01a520d6
ms.contentlocale: ru-ru
ms.lasthandoff: 04/04/2017

---

# <a name="uicheckstate-enumeration"></a>Перечисление UICheckState
Описание состояния флажка элемента интерфейса пользователя для команды.  
   
### <a name="syntax"></a>Синтаксис   
```  
public enum class 
{  
   [DefaultValue(typeid<Microsoft::VisualC::MFC::UICheckState>, "Checked")]  
   Unchecked,   
   Checked,   
   Indeterminate 
};  
```  
   
### <a name="remarks"></a>Примечания  
 [ICommandUI::Check](icommandui-interface.md#check) эти значения используются для описания состояния элемента интерфейса пользователя.    
 Дополнительные сведения об использовании Windows Forms см. в разделе [с помощью пользовательского элемента управления формы Windows в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
   
### <a name="requirements"></a>Требования  
 **Заголовок:** afxwinforms.h (определенный в сборке atlmfc\lib\mfcmifc80.dll)  

