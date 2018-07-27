---
title: Метод FtmBase::UnmarshalInterface | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase::UnmarshalInterface
dev_langs:
- C++
helpviewer_keywords:
- UnmarshalInterface method
ms.assetid: 6850a621-e9a6-4001-bc1e-bd5d1b121adc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 964ce5cc33b51c54446874522317814279cdd960
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33877723"
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