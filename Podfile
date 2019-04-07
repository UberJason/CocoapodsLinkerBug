use_frameworks!

def shared_pods
  pod 'CoreDataStackManager'
end

def ensembles_pods
  pod 'Ensembles/Multipeer'
end

target 'CocoapodsLinkerBug' do
  platform :ios, '11.3'
  shared_pods
end

target 'MyAwesomeKit' do
  platform :ios, '11.3'
  shared_pods
  ensembles_pods
end

target 'Today' do
  platform :ios, '11.3'
  shared_pods
end