---
title: "Метод Module::RegisterWinRTObject | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Module::RegisterWinRTObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RegisterWinRTObject - метод"
ms.assetid: a2782c9c-b9c5-4e4b-9c8d-ef513aea20c5
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Метод Module::RegisterWinRTObject
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Регистрирует один или несколько объектов среды выполнения ([!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]), чтобы другие приложения могли к ним подключиться.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT RegisterWinRTObject(const wchar_t* serverName,  
   wchar_t** activatableClassIds,  
   WINRT_REGISTRATION_COOKIE* cookie,  
   unsigned int count)  
```  
  
#### <a name="parameters"></a>Параметры  
 `serverName`  
 Имя, которое определяет подмножество объектов, затронутых этой операцией.  
  
 `activatableClassIds`  
 Массив активируемых идентификаторов CLSID для регистрации.  
  
 `cookie`  
 Значение, которое идентифицирует зарегистрированные объекты класса. Это значение в дальнейшем используется для отмены регистрации.  
  
 `count`  
 Количество объектов, которое необходимо зарегистрировать.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT (например, CO_E_OBJISREG), указывающее причину неудачного завершения операции.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL
 
 ## <a name="see-also"></a>См. также раздел
 [Класс модулей](../windows/module-class.md)