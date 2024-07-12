# fulfillmenttools-swagger-codegen-sdk-typescript
## examples

```ts
import {
    CoreConfigurationApi,
    CoreCustomServicesApi,
    CoreDocumentSetsApi,
    CoreEventingApi,
    CoreExpiriesApi,
    CoreFacilitiesApi,
    CoreListingsApi,
    CoreNotificationCenterApi,
    CoreProcessesApi,
    CoreProcessesExternalActionsApi,
    CoreProcessesExternalActionsLogsApi,
    CoreRemoteConfigurationApi,
    CoreTagsApi,
    CoreUserManagementApi,
    CoreValidationsApi,
    DOMSCancelationReasonsApi,
    DOMSCheckoutOptionsApi,
    DOMSOrdersApi,
    DOMSRoutingPlansApi,
    FulfillmentOperationsCustomServicesApi,
    FulfillmentOperationsHandoverApi,
    FulfillmentOperationsOperativeProcessApi,
    FulfillmentOperationsPackingApi,
    FulfillmentOperationsRestowApi,
    FulfillmentOperationsReturnsApi,
    FulfillmentOperationsShipmentsApi,
    InfrastructureArtifactsApi,
    InfrastructureFeaturesApi,
    InfrastructureGraphQLApi,
    InfrastructureHealthApi,
    InfrastructureOIDCConfigurationApi,
    InventoryManagementChannelAvailabilityApi,
    InventoryManagementInboundApi,
    InventoryManagementStocksApi,
    LastMileIntegrationCarriersApi
} from "fulfillmenttools-swagger-codegen-sdk-typescript";

const fftAuthUrl = "https://identitytoolkit.googleapis.com/v1/accounts:signInWithPassword?key=";
const fftApiUser: string = process.env.FFT_API_USER;
const fftApiKey: string = process.env.FFT_API_KEY;
const fftApiPwd: string = process.env.FFT_API_PWD;
const fftApiUrl: string = process.env.FFT_API_URL;

const getFetcher = (bearerToken: string) => {
    return (url: string): Promise<Response> => fetch(url, {
        cache: "no-store",
        headers: {
            Authorization: `Bearer ${ bearerToken }`,
            "Cache-Control": "no-cache",
        }
    });
};

const getFftAuthInfo = async () => {
    const authResponse = await fetch(fftAuthUrl + encodeURIComponent(fftApiKey), {
        method: "POST",
        body: JSON.stringify({
            email: fftApiUser + "@" + fftProjectId + ".com",
            password: fftApiPwd,
            returnSecureToken: true,
        }),
        headers: {
            "Content-Type": "application/json",
            "Cache-Control": "no-cache",
        }
    });

    return await authResponse.json();
};

const authInfo = await getFftAuthInfo();

// Examples to instantiate different APIs
new CoreConfigurationApi({}, fftApiUrl, getFetcher(authInfo.idToken));
new CoreCustomServicesApi({}, fftApiUrl, getFetcher(authInfo.idToken));
new CoreDocumentSetsApi({}, fftApiUrl, getFetcher(authInfo.idToken));
new CoreEventingApi({}, fftApiUrl, getFetcher(authInfo.idToken));
new CoreExpiriesApi({}, fftApiUrl, getFetcher(authInfo.idToken));
new CoreFacilitiesApi({}, fftApiUrl, getFetcher(authInfo.idToken));
new CoreListingsApi({}, fftApiUrl, getFetcher(authInfo.idToken));
new CoreNotificationCenterApi({}, fftApiUrl, getFetcher(authInfo.idToken));
new CoreProcessesApi({}, fftApiUrl, getFetcher(authInfo.idToken));
new CoreProcessesExternalActionsApi({}, fftApiUrl, getFetcher(authInfo.idToken));
new CoreProcessesExternalActionsLogsApi({}, fftApiUrl, getFetcher(authInfo.idToken));
new CoreRemoteConfigurationApi({}, fftApiUrl, getFetcher(authInfo.idToken));
new CoreTagsApi({}, fftApiUrl, getFetcher(authInfo.idToken));
new CoreUserManagementApi({}, fftApiUrl, getFetcher(authInfo.idToken));
new CoreValidationsApi({}, fftApiUrl, getFetcher(authInfo.idToken));
new DOMSCancelationReasonsApi({}, fftApiUrl, getFetcher(authInfo.idToken));
new DOMSCheckoutOptionsApi({}, fftApiUrl, getFetcher(authInfo.idToken));
new DOMSOrdersApi({}, fftApiUrl, getFetcher(authInfo.idToken));
new DOMSRoutingPlansApi({}, fftApiUrl, getFetcher(authInfo.idToken));
new FulfillmentOperationsCustomServicesApi({}, fftApiUrl, getFetcher(authInfo.idToken));
new FulfillmentOperationsHandoverApi({}, fftApiUrl, getFetcher(authInfo.idToken));
new FulfillmentOperationsOperativeProcessApi({}, fftApiUrl, getFetcher(authInfo.idToken));
new FulfillmentOperationsPackingApi({}, fftApiUrl, getFetcher(authInfo.idToken));
new FulfillmentOperationsPickingApi({}, fftApiUrl, getFetcher(authInfo.idToken));
new FulfillmentOperationsRestowApi({}, fftApiUrl, getFetcher(authInfo.idToken));
new FulfillmentOperationsReturnsApi({}, fftApiUrl, getFetcher(authInfo.idToken));
new FulfillmentOperationsShipmentsApi({}, fftApiUrl, getFetcher(authInfo.idToken));
new InfrastructureArtifactsApi({}, fftApiUrl, getFetcher(authInfo.idToken));
new InfrastructureFeaturesApi({}, fftApiUrl, getFetcher(authInfo.idToken));
new InfrastructureGraphQLApi({}, fftApiUrl, getFetcher(authInfo.idToken));
new InfrastructureHealthApi({}, fftApiUrl, getFetcher(authInfo.idToken));
new InfrastructureOIDCConfigurationApi({}, fftApiUrl, getFetcher(authInfo.idToken));
new InventoryManagementChannelAvailabilityApi({}, fftApiUrl, getFetcher(authInfo.idToken));
new InventoryManagementInboundApi({}, fftApiUrl, getFetcher(authInfo.idToken));
new InventoryManagementStocksApi({}, fftApiUrl, getFetcher(authInfo.idToken));
new LastMileIntegrationCarriersApi({}, fftApiUrl, getFetcher(authInfo.idToken));
```