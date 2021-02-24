provider "aws" {
  region     = "us-east-1"
  access_key = "AKIAIABYGQFTUHAPMXMA"
  secret_key = "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"
}

data "aws_ami" "ubuntu" {
  most_recent = true

  filter {
    name   = "name"
    values = ["ubuntu/images/hvm-ssd/ubuntu-focal-20.04-amd64-server-*"]
  }

  filter {
    name   = "virtualization-type"
    values = ["hvm"]
  }

  owners = ["099720109477"] # Canonical
}

resource "aws_instance" "web" {
  ami           = data.aws_ami.ubuntu.id
  instance_type = "t2.micro"

  tags = {
    Name = "terraform-server"
  }
}
