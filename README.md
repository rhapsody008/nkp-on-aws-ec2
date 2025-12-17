# Basic Info


# Steps

1. Terraform apply for infra provisioning, get VPC ID and Subnet IDs from output

2. If AMI is not yet available, build the image
```
cd mynkp
tar -xzvf kib.tar.gz -C kib 
cd kib
./konvoy-image create-package-bundle --os ubuntu-22.04 --output-directory=artifacts
./konvoy-image build aws --region ap-southeast-1 images/ami/ubuntu-2204.yaml
```
3. Get the AMI id from generated manifest.json

4. Put VPC ID, Subnet IDs, AMD ID into create.sh

5. Run create.sh

6. `cat ~/mynkp/nkp.conf >> ~/.kube/config`

7. Install Kommander
```
nkp install kommander --init > kommander.yaml
nkp install kommander --installer-config kommander.yaml
```

