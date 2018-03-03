---
title: "Метод FtmBase::UnmarshalInterface | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase::UnmarshalInterface
dev_langs:
- C++
helpviewer_keywords:
- UnmarshalInterface method
ms.assetid: 6850a621-e9a6-4001-bc1e-bd5d1b121adc
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ce3710e84a9f7680b56f461029f279a659a5c14a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ftmbaseunmarshalinterface-method"></a>Метод FtmBase::UnmarshalInterface
Инициализирует только что созданный прокси-сервера и возвращает указатель на интерфейс для прокси-сервера.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
STDMETHODIMP UnmarshalInterface(  
   __in IStream *pStm,  
   __in REFIID riid,  
   __deref_out void **ppv  
) override;  
```  
  
#### <a name="parameters"></a>Параметры  
 `pStm`  
 Указатель на поток, из которого будет распаковать указатель на интерфейс.  
  
 `riid`  
 Ссылка на идентификатор интерфейса необходимо распаковать.  
  
 `ppv`  
 После завершения операции адрес переменной указателя, получающей указатель интерфейса, запрашиваемый в `riid`. Если операция завершилась успешно, *`ppv` содержит указатель на запрошенный интерфейс интерфейса необходимо распаковать.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если успешно; в противном случае возвращается E_NOINTERFACE или E_FAIL.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** ftm.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс FtmBase](../windows/ftmbase-class.md)