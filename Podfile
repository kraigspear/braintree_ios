source 'https://github.com/CocoaPods/Specs.git'

platform :ios, '9.0'
workspace 'Braintree.xcworkspace'
inhibit_all_warnings!

target 'Demo' do
  platform :ios, '9.0'

  pod 'AFNetworking'
  pod 'CardIO'
  pod 'NSURL+QueryDictionary', '~> 1.0'
  pod 'PureLayout'
  pod 'InAppSettingsKit'
  pod 'BraintreeDropIn', :podspec => 'BraintreeDropIn.podspec'
end

abstract_target 'Tests' do
  pod 'Specta'
  pod 'Expecta'
  pod 'OCMock'
  pod 'OHHTTPStubs'

  target 'UnitTests'
  target 'IntegrationTests'
end

post_install do |installer|
  installer.pods_project.targets.each do |target|
    if target.name == "BraintreeDropIn"
      target.build_configurations.each do |config|
        config.build_settings['HEADER_SEARCH_PATHS'] = '${PODS_ROOT}/../BraintreeCore/Public ${PODS_ROOT}/../BraintreeCard/Public ${PODS_ROOT}/../BraintreeUnionPay/Public ${PODS_ROOT}/../BraintreePaymentFlow/Public ${PODS_ROOT}/../BraintreePaymentFlow/Public/LocalPayment ${PODS_ROOT}/../BraintreePaymentFlow/Public/ThreeDSecure ${PODS_ROOT}/../BraintreePayPal/Public ${PODS_ROOT}/Headers/Private ${PODS_ROOT}/Headers/Private/BraintreeDropIn ${PODS_ROOT}/Headers/Public'
      end
    end
  end
end
