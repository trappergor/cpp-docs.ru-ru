---
title: "Метод Module::RegisterCOMObject | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Module::RegisterCOMObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RegisterCOMObject - метод"
ms.assetid: 59f223dc-03c6-429d-95da-b74b3f73b702
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Метод Module::RegisterCOMObject
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Регистрирует один или несколько объектов модели COM, чтобы другие приложения могли к ним подключиться.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
WRL_NOTHROW virtual HRESULT RegisterCOMObject(  
   const wchar_t* serverName,  
   IID* clsids,  
   IClassFactory** factories,  
   DWORD* cookies,  
   unsigned int count);  
  
```  
  
#### <a name="parameters"></a>Параметры  
 `serverName`  
 Полное имя сервера.  
  
 `clsids`  
 Массив регистрируемых идентификаторов CLSID.  
  
 `factories`  
 Массив интерфейсов IUnknown объектов класса, чья доступность публикуется.  
  
 `cookies`  
 После завершения операции представляет массив указателей на значения, которые определяют зарегистрированные объекты класса. Эти значения в дальнейшем используются для отмены регистрации.  
  
 `count`  
 Количество идентификаторов CLSID, которые необходимо зарегистрировать.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT (например, CO_E_OBJISREG), указывающее причину неудачного завершения операции.  
  
## <a name="remarks"></a>Примечания  
 COM-объекты зарегистрированы с помощью перечислителя CLSCTX_LOCAL_SERVER перечисления CLSCTX.  
  
 Тип подключения к зарегистрированным объектам определяется сочетанием текущего параметра шаблона `comflag` и перечислителя REGCLS_SUSPENDED перечисления REGCLS.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL
 
 ## <a name="see-also"></a>См. также
 [Класс модулей](../windows/module-class.md)