Vagrant.configure('2') do |config|
  config.vm.box = 'azure'

  # use local ssh key to connect to remote vagrant box
  config.ssh.private_key_path = '~/.ssh/id_rsa'
  config.vm.define ENV['VM_NAME']  do |t|
  end
  config.vm.provider :azure do |azure, override|

    # each of the below values will default to use the env vars named as below if not specified explicitly
    azure.tenant_id = ENV['AZURE_TENANT_ID']
    azure.client_id = ENV['AZURE_CLIENT_ID']
    azure.client_secret = ENV['AZURE_CLIENT_SECRET']
    azure.subscription_id = ENV['AZURE_SUBSCRIPTION_ID']

    azure.vm_image_urn = 'OpenLogic:CentOS:7.2:latest'
    azure.vm_name = ENV['VM_NAME']
    azure.vm_size = 'Standard_D1_v2'

    azure.resource_group_name = ENV['RG_NAME']
    azure.location = ENV['LOCATION']
    azure.instance_ready_timeout = 600
    # azure.vm_password = ENV['VM_PASSW']
    azure.admin_username = "raci"

  end

end
