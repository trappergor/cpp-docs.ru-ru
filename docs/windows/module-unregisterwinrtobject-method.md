---
title: "Метод Module::UnregisterWinRTObject | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Module::UnregisterWinRTObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "UnregisterWinRTObject - метод"
ms.assetid: 32334aa7-2293-40d2-9a89-4b02e2e31f3c
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Метод Module::UnregisterWinRTObject
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Отменяет регистрацию одного или нескольких объектов среды выполнения ([!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]). Таким образом другие приложения не смогут подключиться к ним.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
virtual HRESULT UnregisterWinRTObject(  
   unsigned int,  
   _Inout_ WINRT_REGISTRATION_COOKIE* cookie  
);  
  
```  
  
#### <a name="parameters"></a>Параметры  
 `cookie`  
 Указатель на значение, определяющее объект класса, регистрация которого должна быть отменена.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL
 
 ## <a name="see-also"></a>См. также
 [Класс модулей](../windows/module-class.md)