---
title: Функция AsWeak | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::AsWeak
dev_langs:
- C++
helpviewer_keywords:
- AsWeak function
ms.assetid: a6f10cfc-c1d6-4761-adb9-1a119cc99913
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a51b7095ec654c4ebb393c9a83d1e30fb52ce019
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39462629"
---
# <a name="asweak-function"></a>AsWeak - функция
Извлекает слабую ссылку на определенный экземпляр.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<typename T>  
HRESULT AsWeak(  
   _In_ T* p,  
   _Out_ WeakRef* pWeak  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 *T*  
 Указатель на тип параметра *p*.  
  
 *p*  
 Экземпляр типа.  
  
 *pWeak*  
 После завершения операции, указатель на слабую ссылку на параметр *p*.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если операция выполнена успешно; в противном случае ошибка HRESULT, указывающее причину сбоя.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)