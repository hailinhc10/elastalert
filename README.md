# python 3.9.5
pyenv Python 3.9.5
# install1
yum install python3-pip -y
# install2
sudo yum install zlib-devel bzip3 bzip3-devel libffi-devel openssl-devel readline-devel sqlite sqlite-devel xz xz-devel
# install3
sudo yum install python3.9.5 python-dev libffi-dev libssl-dev python3-pip python-pip
# install4
pip3 install elastalert2
# install5
pip3 install "setuptools>=11.3"
# install6
pip3 install "elasticsearch>=5.0.0"
# run req.txt
pip3 install -r requirements.txt
# run setup
python3 setup.py install
# create index
elastalert-create-index
# test config and rules
elastalert-test-rule --config config.yaml rules/a.yaml
# test run
python -m elastalert.elastalert --verbose --rule a.yaml
# systemd
vi /lib/systemd/system/elastalert.service
# enable services
ln -s /lib/systemd/system/elastalert.service /etc/systemd/system/elastalert.service
systemctl daemon-reload
systemctl enable elastalert.service
systemctl start elastalert.service
systemctl status elastalert.service
