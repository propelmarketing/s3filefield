## This is a Django FileField model field with custom S3 Attributes.
### How To Use

#### Example
    from s3filefield.fields import S3FileField
    from s3filefield.signals import s3_clean_model

    class Resume(models.Model):
        name = models.CharField(max_length=256)
        product = models.CharField(max_length=256)
        pdf = S3FileField(s3_fields=['name', 'product'])

    pre_delete.connect(s3_clean_model, sender=Resume)

