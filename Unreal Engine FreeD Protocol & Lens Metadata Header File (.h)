#include "CoreMinimal.h"
#include "Camera/CameraComponent.h"

bool UFreeDParserLibrary::ParseFreeDBinaryData(const TArray<uint8>& RawPacket, float& OutZoom, float& OutFocus)
{
    if (RawPacket.Num() < 29)

    {

        return false;

    }

    
    int32 ZoomRaw = (RawPacket[19] << 16) | (RawPacket[20] << 8) | RawPacket[21];
    int32 FocusRaw = (RawPacket[22] << 16) | (RawPacket[23] << 8) | RawPacket[24];


    OutZoom = static_cast<float>(ZoomRaw) / 100.0f;
    OutFocus = static_cast<float>(FocusRaw) / 100.0f; 

   return true;

}

void AMyVirtualCameraActor::UpdateCameraLensFromMetadata(UCameraComponent* CameraComp, float NewFocalLength)

{
    if (CameraComp)

    {

        CameraComp->SetFieldOfView(CameraComp->GetFOVFromFocalLength(NewFocalLength));

  }

}
